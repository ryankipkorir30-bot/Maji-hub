# Maji Hub

A Node.js + Express + SQLite water-hub discovery and ordering platform for Kenya. Includes a public customer website and a protected operations dashboard.

## Requirements
- Node.js 20 or newer
- npm

## Setup
1. Extract the project folder.
2. Run `npm install`.
3. Copy `.env.example` to `.env`.
4. Set a unique `SESSION_SECRET`, `ADMIN_USERNAME`, and strong `ADMIN_PASSWORD`.
5. Run `npm start` and open `http://localhost:3000`.
6. Open `http://localhost:3000/admin/login.html` for administration.

The database is created automatically at `maji_hub.db`; Kenya's 47 counties are seeded on startup. The first administrator is created from the environment variables when the database has no matching username. Existing administrator records are preserved. To create or reset the account matching your environment values, run `npm run admin:reset`.

## Features
- Browse counties and active water hubs.
- View water prices by hub.
- Place delivery or collection orders.
- Choose M-Pesa (pending integration) or cash.
- Admin dashboard with network metrics.
- Create, edit, activate and deactivate hubs.
- Create and update water prices.
- Review orders and update order/payment statuses.
- Receive contact form messages and track follow-up status.
- Session-protected admin API and HTTP security headers.

## Important production notes
- Use HTTPS and set `NODE_ENV=production`.
- Use a strong random session secret and strong administrator password.
- Back up `maji_hub.db` regularly and keep it outside public web hosting.
- The current M-Pesa option records a pending payment only; it does **not** initiate an STK Push or verify a payment. Integrate and verify a payment provider before accepting live payments.
- Customer account registration and self-service order tracking are not included yet.
