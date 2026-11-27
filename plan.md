# CampusConnect — current implementation plan

## Product direction

CampusConnect is a small, practical campus noticeboard. The calendar starts empty and only shows events the campus events team has explicitly shared. Students can create an account, sign in, search, filter by category, and register. The events team has a separate preconfigured admin login and is the only role allowed to publish events.

## Design

The chosen direction is a softer student-led noticeboard rather than a polished SaaS dashboard. Warm paper tones, handout-like date blocks, simple rules, and editorial headlines make the app feel like something a student union could actually maintain. Copy stays direct and a little human: “What’s happening?” and “Share something people can join.”

## Implementation approach

The React client now consumes the CampusConnect tRPC API instead of rendering seeded frontend data. The server owns the current event list, student accounts, sessions, admin credentials, search/filtering, event creation, and basic registration counts.

The public experience begins with a role-aware login screen. Student signup creates a student account and starts a student session. The events-team login uses credentials configured through environment variables. Admin sessions can create events; student sessions can browse, search, filter, and register. The calendar intentionally has no initial events.

The backend store is an in-memory prototype boundary so the interaction can be exercised immediately in Preview. It can later be replaced by the requested PostgreSQL/Spring Boot service without changing the client contract: `campus.me`, `campus.login`, `campus.signup`, `campus.events`, `campus.createEvent`, and `campus.register`.

## Project structure

- `client/src/pages/Home.tsx`: Auth screen, student browse/search view, admin event-sharing view, empty states, and registration actions.
- `client/src/index.css`: Softer campus noticeboard styling and responsive layouts.
- `server/campus.ts`: Campus users, sessions, empty event store, search, event creation, and registration helpers.
- `server/routers.ts`: tRPC API for student/admin auth, event search, event creation, and registration.
- `public/routes.json endpoint`: `/` and `/404` route manifest.
- `server/_core/*`, `drizzle/*`: Existing platform and persistence scaffolding retained as the next integration boundary.
