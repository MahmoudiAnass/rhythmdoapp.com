# RhythmDo brand assets

Save your logo files into this folder with these exact filenames — the site auto-loads them:

| Filename                | Purpose                            | Recommended size          |
| ----------------------- | ---------------------------------- | ------------------------- |
| `logo.png`              | Navbar & footer logo               | 256×256 px (transparent)  |
| `logo.svg`              | Optional vector version (crisper)  | Any                       |
| `favicon.png`           | Browser tab icon                   | 32×32 or 48×48 px         |
| `apple-touch-icon.png`  | iOS home-screen icon               | 180×180 px                |
| `og-cover.png`          | Social share preview (Twitter/FB)  | 1200×630 px               |

## Quick setup

Fastest path from a single source logo:

1. Save the master logo as `logo.png` (transparent background, square, ~512×512+).
2. Copy it and rename to `favicon.png` — a browser will scale it fine.
3. Copy it, resize to 180×180, save as `apple-touch-icon.png`.
4. (Optional) Design a 1200×630 OG cover: dark background, logo left, tagline "Start faster. Keep your rhythm." right — save as `og-cover.png`. Use [canva.com](https://canva.com) with template size **Facebook Cover**.

## Compression

Run PNGs through [tinypng.com](https://tinypng.com) before committing. Icons should be well under 20 KB, OG cover under 200 KB.

## Push to the site

```powershell
git add assets
git commit -m "assets: add logo, favicon, OG cover"
git push
```

Missing files won't crash the site — the img/link tags just show broken icons until you add them.
