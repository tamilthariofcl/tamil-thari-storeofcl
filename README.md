# Tamil Thari e-commerce starter

This is a polished, responsive **front-end prototype** using the supplied Tamil Thari logo and UPI QR image.

## Preview
Open `index.html` in a modern browser. Demo admin password: `thari123`.

## Important: demo vs real store
This first version uses browser `localStorage`. Products, orders, customer details and uploaded payment screenshots stay in that browser and **are not sent to you by email or saved to an online database**. The demo admin password is not secure. Do not use this prototype to accept real customer orders as-is.

## Free-hosting path
1. Create a free GitHub account and a repository named `tamil-thari-store`.
2. Upload `index.html`, the `assets` folder, `supabase-schema.sql`, and this README.
3. In GitHub, open **Settings → Pages**, select deploy from the `main` branch and root folder, then save. GitHub Pages hosts the static front-end free.
4. For a real store, create a Supabase project (free tier), run `supabase-schema.sql` in its SQL Editor, configure Supabase Auth, and implement server-side order submission with an Edge Function. Keep payment screenshots in a **private** Storage bucket.
5. Configure an email provider (for example, Resend) from the server-side Edge Function to notify the owner about a new order. Never place email API secrets in `index.html`.
6. Create the first admin account in Supabase Auth and add its user UUID to `public.store_admins`.
7. Replace the demo browser storage calls with Supabase-backed product, authentication, order, and upload operations. Add server-side validation and rate limiting before going live.

## QR/payment behavior
The supplied QR is shown at checkout. Customers upload a payment screenshot and submit their order. A QR scan alone cannot verify payment; the owner must verify the payment in their UPI app/bank. The real backend should store the screenshot privately and send the owner a secure link, not a public image URL.

## Before launch checklist
- Verify that the uploaded QR belongs to the business UPI account and that the displayed payee name is correct.
- Add shipping, returns, privacy, terms, and contact details.
- Test mobile layout, checkout, admin permissions, image uploads and order emails.
- Do not collect more customer data than necessary; restrict admin access and use HTTPS.
