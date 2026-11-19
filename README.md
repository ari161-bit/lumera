# LUMÉRA

A luxury candle storefront: a React shop front and an Express + Supabase API with customer accounts, orders, reviews, wishlists and discount codes.

**Live:** https://storefront-projects.vercel.app

## Structure

```
server.js            Express API (deployed as a Vercel function)
auth.js              JWT sign-in for customers
db.js                Supabase client
lumera-migrate.sql   database tables
lumera-web/          React + Vite + Tailwind frontend
```

## Run locally

API:

```bash
cp .env.example .env   # fill in SUPABASE_URL, SUPABASE_SERVICE_ROLE_KEY, JWT_SECRET
npm install
npm start
```

Frontend:

```bash
cd lumera-web
npm install
npm run dev
```

Run `lumera-migrate.sql` in the Supabase SQL editor before first use.

## API

| Area | Routes |
|---|---|
| Auth | `POST /api/auth/signup`, `POST /api/auth/login`, `GET /api/auth/me`, `PUT /api/auth/profile`, `POST /api/auth/change-password` |
| Orders | `POST /api/candle-orders`, `GET /api/candle-orders/:id`, `GET /api/my-orders` |
| Reviews | `GET` / `POST /api/candle-reviews` |
| Account | `/api/addresses`, `/api/wishlist` |
| Other | `POST /api/newsletter`, `GET /api/discounts/validate` |
