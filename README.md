<div align="center">

# RhythmDo — Marketing Site

**Start faster. Keep your rhythm.**

The official marketing website for the [RhythmDo](https://play.google.com/store/apps/details?id=com.oushen.rhythmdo) Android app — a focus & productivity app for makers, thinkers, and finishers.

[![Made with HTML](https://img.shields.io/badge/HTML-5-E34F26?logo=html5&logoColor=white)]()
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38BDF8?logo=tailwindcss&logoColor=white)]()
[![No Build Step](https://img.shields.io/badge/build-none-34D399)]()
[![Deploy anywhere](https://img.shields.io/badge/deploy-Vercel%20%7C%20Netlify%20%7C%20cPanel%20%7C%20Pages-A78BFA)]()

</div>

---

## Table of contents
- [Overview](#overview)
- [Pages](#pages)
- [Tech stack](#tech-stack)
- [Project structure](#project-structure)
- [Design system](#design-system)
- [Local development](#local-development)
- [Deployment](#deployment)
  - [Vercel](#vercel-recommended-for-instant-preview)
  - [Netlify](#netlify)
  - [GitHub Pages](#github-pages)
  - [cPanel via GitHub](#cpanel-via-github-what-were-using)
- [Editing content](#editing-content)
- [Delete-account form backends](#delete-account-form-backends)
- [SEO & analytics](#seo--analytics)
- [Updating the site](#updating-the-site)
- [Google Play links](#google-play-links)
- [Pre-launch checklist](#pre-launch-checklist)
- [License](#license)

---

## Overview

A **3-page static marketing site** for the RhythmDo Android app:

- Zero backend — pure HTML + Tailwind CSS.
- Zero build step — Tailwind is loaded via the Play CDN.
- Zero framework — pages are hand-crafted for pixel-level control matching the in-app dark theme.
- Deploys to any host in seconds: Vercel, Netlify, GitHub Pages, or cPanel via GitHub.

The design mirrors the RhythmDo app: dark background, emerald primary, violet & gold accents, gradient rings, and a glowing timer visualization.

---

## Pages

| Route | File | Purpose |
| --- | --- | --- |
| `/` | [`index.html`](index.html) | Landing page — hero, features, how it works, feature deep-dives, Pro pricing, download CTA. |
| `/about` | [`about/index.html`](about/index.html) | About page — mission, three working styles, app-in-numbers counters, contact. |
| `/delete-account` | [`delete-account/index.html`](delete-account/index.html) | **Google Play requirement** — data deletion request form, steps, and data-retention table. |

---

## Tech stack

| Layer | Choice | Why |
| --- | --- | --- |
| Markup | HTML5 | Simple, portable, SEO-friendly. |
| Styling | Tailwind CSS (Play CDN) | No build step, full utility-first power. |
| Fonts | Inter (Google Fonts) | Matches the app's typography. |
| Icons/graphics | Inline SVG + emoji | No image dependencies, tiny page weight. |
| Animation | Pure CSS keyframes | Ring pulse, floating phone mockups, counter animation. |
| Hosting | Static (any provider) | Free tier friendly. |

---

## Project structure

```
rhythmdoLandingpage/
├── index.html                  # Landing page (/)
├── about/
│   └── index.html              # About page (/about)
├── delete-account/
│   └── index.html              # Data deletion page (/delete-account)
├── vercel.json                 # Vercel config (clean URLs + security headers)
├── netlify.toml                # Netlify config (redirects + headers)
├── .htaccess                   # Apache/cPanel rewrites, HTTPS, cache, security
├── .cpanel.yml                 # cPanel Git deploy manifest
├── robots.txt                  # Crawler policy
├── sitemap.xml                 # Sitemap for search engines
├── .gitignore
└── README.md                   # You are here
```

Each page is fully self-contained — the Tailwind config, CSS variables, and inline `<style>` block live at the top of each `index.html`. This keeps deploys simple (no shared assets to sync) at the small cost of a bit of duplication.

---

## Design system

Colors, typography, and effects are locked to the Android app's theme.

### Colors

| Token | Hex | Use |
| --- | --- | --- |
| `bg` | `#06090F` | Page background |
| `surface` | `#0E1117` | Cards |
| `surface2` | `#161B24` | Card variants |
| `card` | `#1F2633` | Elevated cards |
| `emerald1` | `#34D399` | Primary — CTAs, ring, glow |
| `emerald2` | `#047857` | Primary hover |
| `gold` | `#FBBF24` | Streaks, badges, "PRO" chips |
| `violet1` | `#A78BFA` | Level arc, accents |
| `red1` | `#FF6B6B` | Alerts (calm) |
| `text1` | `#E5E7EB` | Primary text |
| `text2` | `#9CA3AF` | Secondary text |
| `outline1` | `#374151` | Borders, dividers |

### Signature effects
- **Gradient**: `linear-gradient(90deg, #34D399, #A78BFA, #FBBF24)` — used on text (`.gradient-text`) and borders (`.gradient-border`).
- **Emerald glow**: `box-shadow: 0 0 32px rgba(52, 211, 153, 0.28)` on CTAs and the hero ring.
- **Dot background**: subtle radial-dot pattern behind heroes (`.dot-bg`).
- **Timer ring**: animated SVG stroke-dashoffset with soft-glow filter.

### Typography
- Font: **Inter** (400–800 weights)
- Hero: `text-5xl md:text-6xl font-extrabold`
- Section headings: `text-3xl md:text-4xl font-semibold`
- Body: `text-base` in `text2`

---

## Local development

No install required. Any of these work:

```powershell
# 1. Just double-click index.html (opens in browser)

# 2. Python 3
python -m http.server 8000

# 3. Node
npx serve .

# 4. PHP
php -S localhost:8000

# 5. VS Code — install "Live Server" extension, right-click index.html → Open with Live Server
```

Then browse to <http://localhost:8000>.

> **Note:** clean URLs like `/about` (without the trailing slash) only work on servers that resolve directories to `index.html`. Locally, use `/about/` with the trailing slash, or open `about/index.html` directly.

---

## Deployment

### Vercel (recommended for instant preview)

1. Push this repo to GitHub (already done — [MahmoudiAnass/rhythmdoapp.com](https://github.com/MahmoudiAnass/rhythmdoapp.com)).
2. Go to [vercel.com/new](https://vercel.com/new) → **Import Git Repository** → select this repo.
3. Framework preset: **Other**. Build command: *(leave empty)*. Output directory: `./`.
4. Click **Deploy**.
5. In **Project Settings → Domains**, add your custom domain (e.g. `rhythmdoapp.com`).

`vercel.json` already handles clean URLs (`/about` works without the slash) and adds baseline security headers.

### Netlify

1. Go to [app.netlify.com](https://app.netlify.com) → **Add new site → Import from Git** → pick this repo.
2. Build command: *(none)*. Publish directory: `.` (root).
3. Deploy. Configure custom domain under **Domain settings**.

`netlify.toml` handles redirects and security headers.

### GitHub Pages

1. In the repo on GitHub → **Settings → Pages**.
2. Source: **Deploy from a branch** → Branch: `main` → Folder: `/ (root)`.
3. Save. Site will be live at `https://mahmoudianass.github.io/rhythmdoapp.com/`.
4. For a custom domain, add a `CNAME` file at repo root containing your domain (e.g. `rhythmdoapp.com`), then configure DNS.

Clean URLs work because every page uses folder-based routes (`/about/index.html`).

### cPanel via GitHub (what we're using)

1. In cPanel, open **Git Version Control** → **Create**.
2. Paste `https://github.com/MahmoudiAnass/rhythmdoapp.com.git` (or SSH URL if you set up keys).
3. Set the **Repository Path** to something like `/home/YOUR_CPANEL_USER/repositories/rhythmdo-site`.
4. Click **Create**.
5. **Edit [`.cpanel.yml`](.cpanel.yml)** — replace `USERNAME` with your actual cPanel username (the deploy path must match your `public_html`):
   ```yaml
   deployment:
     tasks:
       - export DEPLOYPATH=/home/YOUR_CPANEL_USER/public_html/
       - /bin/cp -R index.html $DEPLOYPATH
       - /bin/cp -R about $DEPLOYPATH
       - /bin/cp -R delete-account $DEPLOYPATH
       - /bin/cp -R .htaccess $DEPLOYPATH 2>/dev/null || true
       - /bin/cp -R robots.txt $DEPLOYPATH
       - /bin/cp -R sitemap.xml $DEPLOYPATH
   ```
6. Commit and push the update:
   ```powershell
   git add .cpanel.yml
   git commit -m "chore: set cPanel deploy path"
   git push
   ```
7. Back in cPanel Git → **Manage** → **Pull or Deploy** tab → click **Update from Remote**, then **Deploy HEAD Commit**.
8. Visit your domain — the site is live. `.htaccess` forces HTTPS, adds clean-URL rewrites, and sets cache headers.

**On every future update:** push to GitHub, then click **Deploy HEAD Commit** in cPanel.

---

## Editing content

All copy lives inline in the three `index.html` files — no CMS, no data files.

| To change... | Edit |
| --- | --- |
| Landing headline, features, pricing | [`index.html`](index.html) |
| About mission, working styles, counters | [`about/index.html`](about/index.html) |
| Deletion steps, retention table, form | [`delete-account/index.html`](delete-account/index.html) |
| Privacy policy sections & third-party list | [`privacy/index.html`](privacy/index.html) |
| Colors, gradient, fonts | The `<script>tailwind.config = {...}</script>` block at the top of each file |
| Nav links & footer | Both live at the top and bottom of each page — update all pages in sync |

### Global find-and-replace targets
When rebranding or updating contacts, use VS Code's global search (`Ctrl+Shift+F`) on:
- `contact@rhythmdoapp.com` — support email
- `com.oushen.rhythmdo` — Android package name
- `rhythmdoapp.com` — canonical domain (also in `sitemap.xml`)
- `© 2026` — footer year

---

## Delete-account form backends

The form on `/delete-account` currently submits via `mailto:` — this opens the user's mail client and works with **zero setup**. For a smoother experience, swap in one of these:

### Option A — Formspree (recommended, free tier)
1. Sign up at [formspree.io](https://formspree.io) and create a new form.
2. Copy the endpoint (e.g. `https://formspree.io/f/xyzabc123`).
3. In [`delete-account/index.html`](delete-account/index.html), find the `<form>` and replace:
   ```html
   action="mailto:contact@rhythmdoapp.com"
   method="POST"
   enctype="text/plain"
   ```
   with:
   ```html
   action="https://formspree.io/f/xyzabc123"
   method="POST"
   ```

### Option B — Google Forms embed
1. Create a Google Form with the same fields (email, reason, notes).
2. Get the embed `<iframe>` code from **Send → Embed**.
3. Replace the entire `<form>…</form>` block in the delete-account page with the iframe.

### Option C — Own backend
If you spin up any endpoint that accepts POST, just point the form's `action` at it.

---

## SEO & analytics

- **`sitemap.xml`** and **`robots.txt`** at the repo root tell crawlers where to look. Update the URLs inside `sitemap.xml` to your production domain.
- **OpenGraph tags** are set in the landing page's `<head>` — customize the `og:image` URL once you have a share image (recommended: 1200×630px).
- **Analytics**: none included. To add Plausible / Umami / GA4, drop the snippet before `</head>` in each page.

---

## Updating the site

```powershell
# from the project folder
git add .
git commit -m "content: update pricing copy"
git push
```

Then, depending on your host:
- **Vercel / Netlify / GitHub Pages** → auto-deploy on push.
- **cPanel** → open Git Version Control → **Pull or Deploy** → **Deploy HEAD Commit**.

---

## Google Play links

| Purpose | URL |
| --- | --- |
| Store listing | <https://play.google.com/store/apps/details?id=com.oushen.rhythmdo> |
| Play badge (English) | <https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png> |
| Package name | `com.oushen.rhythmdo` |

---

## Pre-launch checklist

- [x] ~~Replace `contact@rhythmdo.app`~~ — done, all pages now use `contact@rhythmdoapp.com`.
- [x] ~~Update the canonical domain~~ — done, `sitemap.xml` + OpenGraph now use `rhythmdoapp.com`.
- [ ] Update `USERNAME` → real cPanel user in [`.cpanel.yml`](.cpanel.yml).
- [ ] Choose a form backend for the deletion page (Formspree / Google Form) — see [above](#delete-account-form-backends).
- [ ] Set up the custom domain on your host (Vercel / cPanel).
- [ ] Submit the sitemap in [Google Search Console](https://search.google.com/search-console).
- [ ] Paste the deletion-page URL (`https://rhythmdoapp.com/delete-account/`) and the privacy URL (`https://rhythmdoapp.com/privacy/`) into the Google Play Console **App content → Data safety** and **Privacy policy** fields.
- [ ] (Optional) Add an OG share image at `og-cover.png` and update the `og:image` meta tag.
- [ ] (Optional) Wire up analytics.

---

## License

© 2026 RhythmDo. All rights reserved.

The RhythmDo name, logo, and brand assets are the property of the RhythmDo team. The site source code is provided for reference and deployment of the official RhythmDo marketing site only.
