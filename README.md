# TownMart 🛒

TownMart is a React/Vite storefront being prepared for real local-shop use. Fulfillment is **pickup**, payment is **UPI QR with manual UTR verification**, and admin access is intended to be separate from customer access.

## Run locally

1. Install Node.js (LTS).
2. Download this repository and open the folder in a terminal.
3. Run `npm install`.
4. Run `npm run dev` and open the localhost URL printed by Vite.

## Supabase setup (in progress)

1. Create a Supabase project.
2. Copy `.env.example` to `.env.local` and set `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` from the Supabase project API settings.
3. Run `supabase/schema.sql` in the Supabase SQL Editor.
4. Create the admin user through Supabase Authentication, then promote that user's UUID to role `admin` in the SQL Editor. Do not enable public admin registration.
5. Never put a Supabase service-role key, admin password, or payment secret in client-side code or GitHub.

## Current limitations

The current storefront is still being migrated from browser-local demo storage to Supabase. Do not use it for real customer orders until authentication, database operations, stock handling, and payment verification are implemented and tested. The QR payment flow requires your actual shop QR image; UTR entry alone does not verify that money was received. Deployment is intentionally on hold until the owner approves it.
