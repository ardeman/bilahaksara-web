# Bilah Aksara — public site

Marketing landing + privacy policy for **Bilah Aksara** (`com.ardeman.bilahaksara`).

Static HTML/CSS. No build step.

| Path | Page |
| --- | --- |
| `/` | Landing (ID + light EN, coming soon) |
| `/privacy/` | Kebijakan privasi / Privacy policy |

## Local preview

```bash
# any static server, e.g.
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy to Cloudflare Pages

### One-shot (direct upload)

Requires [Wrangler](https://developers.cloudflare.com/workers/wrangler/) logged in (`npx wrangler login`).

```bash
npx wrangler pages project create bilahaksara-web --production-branch=main
npx wrangler pages deploy . --project-name=bilahaksara-web --branch=main
```

**Live:** https://bilahaksara-web.pages.dev/  
**Privacy:** https://bilahaksara-web.pages.dev/privacy/

### Git-connected (auto-deploy on push)

1. Push this repo to GitHub (public).
2. [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Select `ardeman/bilahaksara-web`, production branch `main`.
4. Build settings: **Framework preset** = None; **Build command** empty; **Build output directory** = `/` (or leave empty / `.`).
5. Save and deploy. Later pushes to `main` redeploy automatically.

Custom domain (optional): Pages project → **Custom domains** → add your domain and follow DNS prompts.

## Privacy URL for stores

Use the live privacy page in Google Play Console and App Store Connect:

`https://<your-pages-host>/privacy/`

Contact email on the page: `are.theman@gmail.com` (change in `privacy/index.html` if needed).

## Notes

- Do not put real historical place/people names in public marketing copy.
- Indonesian first; English is a short gloss / privacy mirror only.
- No store badges until listings exist.
