# afpmanager.com

Static marketing/business page for AFP Manager (Zaiontek LLC). Plain HTML + CSS (Tailwind via CDN) — no build step, deployed via GitHub Pages.

## Deploy

1. Push this repo to GitHub (public, so a custom domain works on the free plan).
2. Repo → Settings → Pages → Source: **Deploy from a branch** → `main` / `(root)`.
3. Settings → Pages → Custom domain: `afpmanager.com` (this repo's `CNAME` file already has it). Enable **Enforce HTTPS** once available.

## DNS (Cloudflare)

- Apex `afpmanager.com` → A records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (optionally AAAA to `2606:50c0:8000::153` .. `2606:50c0:8003::153`).
- `www.afpmanager.com` (optional) → CNAME to `<github-username>.github.io`.
- Set records to **DNS-only** (grey cloud) until GitHub confirms HTTPS is issued, then optionally re-enable the Cloudflare proxy with SSL mode **Full (strict)**.
- Does not affect `app.afpmanager.com` or other subdomains — those stay on the existing Cloudflare Tunnel.
