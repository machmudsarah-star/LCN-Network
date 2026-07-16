# LCH Network and Volunteer Hub

A self-contained, password-protected contact tracker with an AI chat assistant for adding and searching contacts.

## Deploy

This is a single static file — no build step, no dependencies to install.

**GitHub Pages**
1. Create a new GitHub repo and push this folder's contents — **including the hidden `.nojekyll` file** (it must sit next to `index.html` at the repo root; some file explorers hide dotfiles, so make sure it's actually committed). This stops GitHub's default Jekyll build from mangling the app's code.
2. Repo → Settings → Pages → Deploy from branch → `main` / root.
3. Your site will be live at `https://<username>.github.io/<repo-name>/`.

If the password screen doesn't work after deploying, double-check `.nojekyll` was actually pushed (`git status` / GitHub's file list should show it).

**Any static host (Netlify, Vercel, S3, etc.)**
Upload `index.html` as the site root — no config needed.

## Notes
- Contact data is stored in the visitor's browser (localStorage) — it is per-device, not shared automatically across users.
- Password gate is client-side (for casual protection, not high-security use).
- To change the password, edit the `PASSWORD` value inside `index.html`.
