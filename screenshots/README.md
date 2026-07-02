# RhythmDo app screenshots

The landing page gallery loads five numbered images from this folder:

| Filename   | Source                                                    |
| ---------- | --------------------------------------------------------- |
| `01.png`   | Play Store marketing shot #1 (device frame + copy baked in) |
| `02.png`   | Play Store marketing shot #2                              |
| `03.png`   | Play Store marketing shot #3                              |
| `04.png`   | Play Store marketing shot #4                              |
| `05.png`   | Play Store marketing shot #5                              |

## Replacing / adding images

- Overwrite `01.png` – `05.png` with new versions using the same filenames — no HTML changes needed.
- To add a 6th image, add `06.png` here and duplicate one `<figure>` block in `index.html` (search for `screenshots/05.png`).

## Recommended specs
- **Format**: PNG (preferred) or JPG
- **Aspect ratio**: portrait (9:19.5 works well; the current AppScreens output is landscape-ish marketing frames and looks fine too)
- **Width**: ~1080 px is plenty (the site displays them at ~260–290 px wide)
- **File size**: keep each under ~500 KB if you can — compress with [tinypng.com](https://tinypng.com) or [squoosh.app](https://squoosh.app). Current files are ~2–3 MB straight from AppScreens; compressing them is a quick win.

## Publishing

From the project root:

```powershell
git add screenshots
git commit -m "assets: update app screenshots"
git push
```

Vercel / Netlify / GitHub Pages auto-deploy on push; on cPanel, click **Deploy HEAD Commit**.
