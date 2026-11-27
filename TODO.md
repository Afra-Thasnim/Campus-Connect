# CampusConnect TODO

## Student experience

- [x] The calendar starts empty and only displays events that have been shared by the events team.
- [x] Students can create a student account with name, email, and password.
- [x] Students can sign in and sign out through the student flow.
- [x] Students can search events, places, and people through a backend-backed query.
- [x] Students can filter the backend event list by Academic, Community, Sport, Arts, and Career.
- [x] Students can see a clear empty state when no events exist or when a search/category filter has no match.
- [x] Students can save a spot or join the waitlist for a shared event.

## Events-team experience

- [x] The events team has a separate login with the preconfigured admin credentials.
- [x] Only the admin role can access the event-sharing page.
- [x] Admins can share an event with title, category, date, time, venue, description, and capacity.
- [x] Sharing an event writes it through the backend and makes it visible in the student calendar.
- [x] The admin page shows an empty state before the first event is shared and a list of shared events afterward.

## UX and delivery

- [x] The UI uses a softer student-led noticeboard style rather than a polished SaaS dashboard aesthetic.
- [x] The experience is responsive on desktop and mobile widths.
- [x] The route manifest endpoint declares the complete page route set.
- [x] The project runs through the configured development server on port 3000.
- [x] TypeScript diagnostics and the production build pass.
- [x] Browser verification covered student signup, empty calendar, admin login, event sharing, student visibility, and search.

## Registrations and event management

- [x] Student signup collects name, class/course, department, year of study, and roll number.
- [x] A reservation is linked to the signed-in student profile and prevents duplicate reservations.
- [x] The admin can open an event and see each registrant's name, email, class, department, year, roll number, and confirmed/waitlisted status.
- [x] The admin can delete/cancel an event from its detail view.
- [x] Event deletion requires a cancellation reason and removes the event and its active reservation list from the calendar.

## Admin export

- [x] Admins can download the active event's registered and waitlisted student list as a CSV file, including event metadata, student identity, academic details, status, and registration timestamp.
