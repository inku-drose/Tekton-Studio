# Tekton Studio — website

Static marketing site for Tekton Studio (Bengaluru). Plain HTML/CSS/JS — no build step, no dependencies.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole site (styles and scripts inline) |
| `404.html` | Not-found page |
| `site.webmanifest`, `*.png`, `favicon.svg` | Icons and PWA manifest |
| `og-image.png` | Social share preview image |
| `robots.txt`, `sitemap.xml` | SEO |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll) |
| `render.yaml`, `_headers` | Hosting config for Render / Netlify / Cloudflare Pages (ignored by GitHub Pages) |

## Run locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy on GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repo go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. The site goes live at `https://<username>.github.io/<repo>/` within a minute or two.

All asset paths are relative, so the site works both at that sub-path and at a domain root.

### Custom domain (tektonstudio.in)

The canonical URL, Open Graph tags, `sitemap.xml` and `robots.txt` point at `https://tektonstudio.in/`.
To serve the site there:

1. In **Settings → Pages → Custom domain**, enter `tektonstudio.in` (GitHub creates a `CNAME` file).
2. At your DNS provider, add `A` records for `@` pointing to `185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153`, and a `CNAME` record for `www` pointing to `<username>.github.io`.
3. Tick **Enforce HTTPS** once the certificate is issued.

### Note on security headers

GitHub Pages does not support custom response headers, so the headers in `_headers` / `render.yaml`
(`X-Frame-Options`, `Permissions-Policy`, etc.) only apply on Render, Netlify or Cloudflare Pages.
