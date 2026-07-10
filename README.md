# Collins OS — collinsos.com

Marketing site for Collins. Static, single-page, no build step.

## Structure
```
index.html            # the whole site (inline CSS + JS)
assets/
  collins-mark.png    # logo icon (transparent) — nav, footer, favicon
  collins-icon-512.png # favicon / apple-touch-icon
  og-image.png        # social share image (1200×630)
CNAME                 # custom domain for GitHub Pages
```

## Deploy

### Option A — GitHub Pages (git-native, free)
1. Create a new repo and push these files to `main`.
2. Repo **Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / root.
3. The included `CNAME` sets the domain to `collinsos.com`. In your DNS, add:
   - `A` records for the apex `collinsos.com` → GitHub Pages IPs
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` → `<your-username>.github.io`
4. Enable **Enforce HTTPS** once the cert provisions.

### Option B — Netlify / Vercel / Cloudflare Pages
1. Push to a repo, connect it in the host's dashboard.
2. No build command; publish directory = repo root.
3. Add `collinsos.com` as a custom domain and follow the DNS prompt.
Every push to `main` redeploys automatically.

## Notes
- Fonts load from Google Fonts (Inter + Manrope) via CDN.
- Replace `og-image.png` if the messaging changes; it's referenced absolutely at
  `https://collinsos.com/assets/og-image.png` in the `<head>` meta tags.
