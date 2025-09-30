# Zantra Bookings – Coding Agents Context

This file defines guardrails and shared context for coding agents
(Codex/GPT) working on the Zantra Bookings repo.

## Project Overview
- Name: Zantra Bookings
- Type: Local-first SaaS booking and invoicing app
- Stack: Single-file HTML (Tailwind CSS, Chart.js, jsPDF, IndexedDB, Supabase)
- Features: Bookings, invoices, payments, reports, settings
- Monetization: Stripe subscription → Supabase Auth user provisioning
- Requirement: Always enforce login before showing app

## Core Principles
1. Offline-first: IndexedDB as primary storage.
2. Cloud sync: Supabase push/pull when connected.
3. Auth required: Block all features until login is successful.
4. Atomic updates: Changes delivered as full-file PRs (no partial snippets).
5. Consistency: Utility functions (DateUtils, Toast, Theme) standardized.
6. Security: Only use Supabase anon key in frontend; never expose service key.
7. Branding: Deep purple theme with Zantra logo in header.

## Agent Prompt Roadmap
- PR1: Refactor utilities into shared core block.
- PR2: Implement Chart.js for reporting.
- PR3: Add Supabase Auth (login/logout).
- PR4: Add sync layer (dirty flags + last-write-wins).
- PR5: Enforce subscription check via Supabase profile.
- PR6: UX polish (defaults, logo, responsive design).

## Deliverables
- Always return the entire updated zantra_bookings.html file.
- No placeholders, ellipses, or truncated sections.
- Must be ready-to-run in browser with Supabase project credentials.
