# nova-website

Frontend for **Nova** — AI personal secretary for real estate agents in CDMX.  
Built by Mesa Digital. Backend lives at `rtopaz/mesa-digital`.

## Files

| File | Description |
|------|-------------|
| `index.html` | Marketing landing page — public |
| `panel.html` | Agent dashboard — requires `?client=SLUG&token=TOKEN` |
| `dashboard.html` | Operator dashboard — password protected (`nova2026`) |
| `_redirects` | Netlify redirect rules |
| `netlify.toml` | Netlify build config and headers |

## URLs (Netlify)

- Landing: `novadigital.com.mx`
- Agent panel: `novadigital.com.mx/panel.html?client=SLUG&token=TOKEN`
- Operator: `novadigital.com.mx/dashboard.html`
- Demo panel: `novadigital.com.mx/p/demo`

## API

All panel data loads from `https://mesa-digital-ke7b.onrender.com`.  
Falls back to sample data if API is unreachable.

## Nova WhatsApp number

+52 777 991 6778 (Phone Number ID: 1091589807369689)

## Day 2 — what was built

- Landing page with live WhatsApp chat simulation in hero
- Agent dashboard: Post cards, Email cards, Lead cards + quick actions + listings + expenses
- Operator dashboard: client grid, pending table, new client modal, MRR counter

## Day 3 — what's next

- Listings manager: wire `/nova/listings/:slug` GET/POST for real data
- PDF ingestion: agent sends PDF → caption "propiedad" → Claude Vision → saved to listings
- Image enhancement: rename styles Profesional / Premium in `imageEnhancer.js`
- Wire operator dashboard "Nuevo cliente" to real `POST /admin/create-client` endpoint
- Add `POST /admin/nova-clients` endpoint in `server.js` (returns all real_estate clients)

## Backend routes (already live)

- `GET /nova/listings/:slug`
- `POST /nova/listings/:slug`
- `PATCH /nova/listings/:id/status`
- `DELETE /nova/listings/:id`
- `GET /nova/expenses/:slug`
