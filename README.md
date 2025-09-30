# Zantra Bookings

Zantra Bookings is a local-first SaaS app for managing bookings,
invoices, and payments. It runs in the browser as a single-file HTML
application with offline support via IndexedDB and cloud sync via
Supabase.

## Features
- Bookings: Create, edit, and manage bookings.
- Invoices: Auto-generate invoices and track payment status.
- Payments: Record payments and methods, generate receipts.
- Reports: View revenue and activity trends (Chart.js).
- Offline-first: Works without internet using IndexedDB.
- Cloud sync: Supabase sync when online.
- Auth required: Users must log in to access.
- Stripe billing: Subscription required to activate accounts.

## Tech Stack
- Frontend: HTML, TailwindCSS, Chart.js, jsPDF, IndexedDB
- Backend: Supabase (Postgres, Auth, Storage)
- Payments: Stripe Checkout → Webhook → Supabase provisioning

## Setup
1. Clone repo:
   git clone https://github.com/your-org/zantra-bookings.git
2. Open `zantra_bookings.html` in a modern browser.
3. Add your Supabase project URL and anon key into the <script> block:
   const supabaseUrl = "https://your-project.supabase.co";
   const supabaseKey = "your-anon-key";
   const supabase = supabase.createClient(supabaseUrl, supabaseKey);
4. Configure Supabase tables and RLS policies (see /schema.sql).
5. Set up Stripe products and webhook handler (to auto-provision users).
6. Host the file on GitHub Pages, Netlify, or Vercel.

## Development Workflow
- PR1: Core cleanup & utility extraction
- PR2: Replace manual charting with Chart.js
- PR3: Supabase authentication (login/logout flow)
- PR4: Sync layer (offline IndexedDB + cloud merge)
- PR5: Stripe subscription enforcement
- PR6: UX polish (branding, defaults, responsive)

## License
Proprietary © Zantra
