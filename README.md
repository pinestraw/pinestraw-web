# pinestraw-web

The Pinestraw website: plain static HTML and CSS, no build step.

- `index.html`: the site
- `styles.css`: all styles (light and dark mode)
- `404.html`, `favicon.svg`

## Run locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. Or open `pinestraw-web.code-workspace` in VS Code and use the Live Server extension.

## Hosting

Hosted free on GitHub Pages, serving the root of the `main` branch. Every push to `main` redeploys within a minute or two.

## Pointing the domains

GitHub Pages serves one custom domain per site. Use `pinestraw.enterprises` as the main one and redirect `pinestraw.org` to it.

1. **pinestraw.enterprises**: at the registrar, add these DNS records:
   - `A` records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `pinestraw.github.io`
2. In the repo: Settings → Pages → Custom domain → `pinestraw.enterprises`, then tick **Enforce HTTPS** once the certificate is issued.
3. **pinestraw.org**: use the registrar's free URL forwarding (301) to `https://pinestraw.enterprises`. If the registrar has no forwarding, a free Cloudflare account can do the redirect with a Redirect Rule.

Optional: verify the domain under the org's Settings → Pages to stop anyone else claiming it on GitHub Pages.
