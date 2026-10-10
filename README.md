# RZIA'S AURA — New Storefront

A fresh React + TypeScript + Vite storefront designed for Netlify, with Netlify Functions and Netlify Blobs for shared product/content storage.

## Important setup before production

This project intentionally does **not** include an admin password or token in the source code. Set these in Netlify Site configuration → Environment variables:

- `ADMIN_USERNAME` — your chosen admin username
- `ADMIN_PASSWORD` — a new, strong admin password
- `ADMIN_TOKEN` — a long random secret (at least 32 random characters)

Redeploy after setting them. Do not share these values or put them in frontend code.

## Deploy

1. Upload this ZIP to a new GitHub repository, or extract it locally and push all files to a repository.
2. In Netlify, create a new site from that repository.
3. Build command: `npm run build`
4. Publish directory: `dist`
5. Set the three environment variables above and redeploy.

Netlify Blobs persistence requires a deployed Netlify site. The local Vite dev server does not provide these serverless functions; the browser keeps a preview copy in local storage if the API is unavailable. That preview copy is **not** shared between customers and must not be treated as production storage.

## Included

- Responsive luxury fashion storefront and original RZIA'S AURA styling
- Category browsing, search, product detail, wishlist toggle, cart and WhatsApp order handoff
- PKR, BDT and EUR prices per product
- Separate admin login, product CRUD, multiple image upload, collections, homepage settings, policies and FAQs
- Netlify Blobs shared data and image storage
- Save verification and error messages

## Limitations that require additional production integration

- Online card payment gateway is not configured.
- Customer account registration/login, automated order records, transactional email, shipment tracking integrations, newsletter provider, tax calculations, and advanced inventory/order workflows are not included in this starter.
- WhatsApp checkout is an inquiry/handoff, not a payment processor or automatic order database.
- Before public launch, add rate limiting and secure session/cookie-based authentication (the starter uses a bearer token kept in sessionStorage), review privacy/security, and test with real products and devices.
- Product image URLs and collection images use sample Unsplash imagery until replaced in admin.
