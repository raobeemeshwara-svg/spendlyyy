# Spendly
by Utla Beemeshwara Rao

A colourful expense tracker: daily, weekly and monthly spending, budgets, savings goals, saving quotes, reminders (while the app is open), and a 30-day free trial then ₹49/month.

## Files
- `index.html` — the whole website (no build step, no login, no database).

## Deploy on Vercel
1. Upload `index.html` (and this README) to a new GitHub repository.
2. On vercel.com choose Add New > Project > import the repository > Deploy (Framework: Other).
3. Open the link Vercel gives you.

## Notes
- Data is saved in each visitor's own browser (localStorage). It does not sync between devices.
- Payments (manual): customer pays your UPI ID, taps "I have paid", you get a WhatsApp message, check your bank, then open `your-site/#owner`, enter your PIN and the transaction ID to get a 6-digit unlock code and send it to them.
- Fill in `UPI_ID`, `OWNER_WA`, `SECRET` and `OWNER_PIN` near the top of the script in `index.html`. Optionally add your QR image as `qr.png` in the repo.
- This is not tamper-proof (the secret is visible in the page source). Move to a payment gateway with accounts when the business grows.
- The free trial runs in the browser, so it can be reset by clearing site data. Real payment enforcement needs accounts and a server.

## Ask Spendly (AI assistant)
- Frontend is in `index.html`; the server function is `api/ask.js`.
- In Vercel > Settings > Environment Variables add `ANTHROPIC_API_KEY` (from console.anthropic.com), then redeploy.
- The key must never be placed in `index.html`. API usage is billed separately by Anthropic.
- Payment questions show Contact buttons (WhatsApp, Email, Call) with the owner's details.
