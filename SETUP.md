# PNLE Review — Real Backend Setup

This build uses Supabase Auth and Postgres. GitHub Pages can host `index.html`; Supabase handles authentication and per-user data.

## 1. Create Supabase project
Create a project at https://supabase.com/

## 2. Run the database schema
In Supabase Dashboard → SQL Editor, run `supabase/schema.sql`.

The schema enables Row Level Security. Every `study_state` row is keyed by the authenticated user's UUID and policies only allow `auth.uid()` to access its own row.

## 3. Enable Email authentication
Authentication → Providers → Email → enable it. Choose whether email confirmation is required. Set the Site URL and redirect URL to your GitHub Pages URL.

## 4. Configure the frontend
Open `index.html` and replace:

`https://YOUR-PROJECT.supabase.co`

with your Supabase Project URL, and replace `YOUR_SUPABASE_ANON_KEY` with the Supabase **anon/public** key.

Never put the `service_role` key in `index.html`. The anon key is designed for frontend use when RLS is configured correctly.

## 5. GitHub Pages
Upload `index.html` and the `supabase/` folder. Keep the original V3 backup.

## Per-user data
The app stores its study state in `public.study_state`. The browser does not choose another user's ID; the authenticated Supabase user ID is used by the frontend, and RLS independently enforces the same ownership rule in the database.

## Production note
For stronger account policies, also enable email confirmation, MFA, rate limits, and breached-password protection in Supabase as appropriate for your project.
