# RhythmDo — Landing Site

Marketing site for the RhythmDo Android app.

## Pages
- `/` — Landing
- `/about` — About
- `/delete-account` — Data deletion (Google Play requirement)

## Stack
Pure static HTML + Tailwind CSS (via Play CDN). No build step. Deploys anywhere.

## Local preview
Open `index.html` directly, or run any static server:

```powershell
# Python 3
python -m http.server 8000

# Or Node
npx serve .
```

Then visit http://localhost:8000

## Deploy — Vercel (recommended)
1. Push this repo to GitHub.
2. Import the repo in Vercel — no build settings needed, framework preset: **Other**.
3. Add your custom domain (e.g. `rhythmdo.app`).

`vercel.json` is included for clean URLs.

## Deploy — Netlify
1. Push to GitHub, connect in Netlify.
2. Build command: *(none)*, publish directory: `.`
3. Clean URLs work automatically via folder-based routes.

`netlify.toml` is included.

## Deploy — GitHub Pages
Enable Pages in the repo settings, source = `main` branch, folder = `/` (root).
Clean URLs work because each page uses `/<slug>/index.html`.

## Deploy — cPanel via GitHub
1. In cPanel, open **Git Version Control** → **Create** → paste the GitHub repo URL, set deployment path to `public_html` (or a subfolder).
2. Add a `.cpanel.yml` at repo root (already included) so cPanel copies files on deploy.
3. In cPanel Git, click **Manage** → **Pull or Deploy** → **Deploy HEAD Commit** after each push.

## Editing content
All copy lives inline in the three `index.html` files. Colors are set as CSS variables in the `<style>` block of each page.

## Google Play links
- Listing: https://play.google.com/store/apps/details?id=com.oushen.rhythmdo
- Badge: https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png

## TODO before launch
- Replace `contact@rhythmdo.app` with real contact email (in `about/index.html` and `delete-account/index.html`).
- Optionally embed a Google Form or Formspree endpoint in `delete-account/index.html` (currently the form posts to `mailto:` as a safe default).
