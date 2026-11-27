# CampusConnect

CampusConnect is a campus event noticeboard with separate student and events-team access. Students create a profile, discover events, reserve spots, and join waitlists. The events team publishes events, reviews registrants, downloads CSV lists, and cancels events with a reason.

## Local setup

1. Install dependencies with `pnpm install`.
2. In PowerShell, copy the example file with `Copy-Item .env.example .env`. Edit `.env` to set your own admin email and a long, unique password.
3. Start the development server in PowerShell:

   ```powershell
   $env:NODE_ENV = "development"; pnpm exec tsx watch server/_core/index.ts
   ```

4. Open [http://localhost:3000](http://localhost:3000).

The `.env` file is ignored by Git. Do not commit it; configure `ADMIN_EMAIL` and `ADMIN_PASSWORD` as environment variables in your hosting provider when deploying.


