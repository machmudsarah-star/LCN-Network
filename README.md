# LCH Network and Volunteer Hub — live chat version

This version's chat calls Anthropic's Claude API through a small serverless
function, so it works once deployed anywhere — not just inside Claude's
preview. You need your own Anthropic API key (from console.anthropic.com).

## Deploy to Vercel (get a public link in ~3 minutes)

1. Push this folder's contents to a new GitHub repo (include `api/chat.js`,
   `vercel.json`, and `index.html` — and the hidden `.nojekyll` file if you
   also plan to mirror this to GitHub Pages).
2. Go to vercel.com → **Add New → Project** → import that GitHub repo.
3. Before deploying, open **Environment Variables** and add:
   - `ANTHROPIC_API_KEY` = your key from console.anthropic.com
4. Click **Deploy**. Vercel gives you a public `https://<project>.vercel.app`
   link immediately — that link is shareable and the chat will work for
   anyone who opens it.

No other configuration needed — `vercel.json` and `api/chat.js` are already
set up as a serverless endpoint at `/api/chat`, which `index.html` calls
automatically.

## Notes
- Contact data still lives in each visitor's own browser (localStorage) —
  it is not shared between different people's devices.
- The password gate (`PanConCafe2026`) still applies client-side.
- Your Anthropic API key is only ever read on the server side (`api/chat.js`)
  — it is never exposed to the browser.
- Anthropic API usage on your key is billed per your Anthropic account plan.
