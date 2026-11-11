# Tekvara Studio — website

Static marketing site for Tekvara Studio (Bengaluru). Plain HTML/CSS/JS — no build step, no dependencies.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole site (styles and scripts inline) |
| `404.html` | Not-found page |
| `site.webmanifest`, `*.png`, `favicon.svg` | Icons and PWA manifest |
| `og-image.png` | Social share preview image |
| `robots.txt`, `sitemap.xml` | SEO |
| `render.yaml` | Render hosting config (static site + security headers) |
| `_headers` | Same headers for Netlify / Cloudflare Pages, if ever needed |

## Run locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deployment

Live at **https://tekvara-studio.onrender.com/** — a Render static site defined by `render.yaml`
(Blueprint). Every push to `main` redeploys automatically. Security headers come from `render.yaml`.

The canonical URL, Open Graph tags, structured data, `sitemap.xml` and `robots.txt` all use
`https://tekvara-studio.onrender.com/`. If the site ever moves to another address, find and replace
that URL in `index.html`, `robots.txt` and `sitemap.xml`.
