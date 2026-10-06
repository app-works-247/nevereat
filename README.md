# NeverEat — Official Web Pages

Landing page and official policies for NeverEat.

## Pages Included
- **`docs/index.html`**: Landing page with product presentation, features, and FAQ.
- **`docs/privacy.html`**: Privacy Policy.
- **`docs/terms.html`**: Terms of Service.
- **`docs/style.css`**: Shared styles, theme variables, and responsive layout.

> The copies of these files at the repository root are **not published**. Only
> `docs/` is served. Edit the files in `docs/`.

## Deployment
- **GitHub Pages**: Source is `Deploy from a branch` -> `main` / **`/docs`**.
  (Verified: `/README.md` and `/docs/index.html` both 404 on the live site,
  while `/style.css` and `/privacy.html` resolve — so `docs/` is the site root.)
- **Vercel / Cloudflare Pages / Netlify**: set the output/publish directory to `docs`.

## app-ads.txt

Not in this repo. It lives in
[`app-works-247/app-works-247.github.io`](https://github.com/app-works-247/app-works-247.github.io)
and is served at <https://app-works-247.github.io/app-ads.txt>.

Ad-network crawlers take the developer website from the App Store listing
(`https://app-works-247.github.io/nevereat/`), drop the path and fetch
`/app-ads.txt` at the host root. A copy under `/nevereat/` is never read, so do
not add one here: it would only drift from the real file.
