# NeverEat — Official Web Pages

Landing page and official policies for NeverEat.

## Pages Included
- **`docs/index.html`**: Landing page with product presentation, features, and FAQ.
- **`docs/privacy.html`**: Privacy Policy.
- **`docs/terms.html`**: Terms of Service.
- **`docs/style.css`**: Shared styles, theme variables, and responsive layout.
- **`docs/app-ads.txt`**: Authorized digital sellers (see below).

> The copies of these files at the repository root are **not published**. Only
> `docs/` is served. Edit the files in `docs/`.

## Deployment
- **GitHub Pages**: Source is `Deploy from a branch` -> `main` / **`/docs`**.
  (Verified: `/README.md` and `/docs/index.html` both 404 on the live site,
  while `/style.css` and `/privacy.html` resolve — so `docs/` is the site root.)
- **Vercel / Cloudflare Pages / Netlify**: set the output/publish directory to `docs`.

## app-ads.txt

`docs/app-ads.txt` declares who is allowed to sell NeverEat's ad inventory. It
holds the publisher's own AdMob line plus the full Appodeal mediation list
(~2,500 records, from <https://appodeal.com/app-ads.txt>).

**It only counts when served from the root of a domain**, because ad-network
crawlers read the developer website URL from the App Store listing, reduce it to
the bare domain and fetch `https://<domain>/app-ads.txt`. They never look inside
a subdirectory.

That makes the current project-page URL (`app-works-247.github.io/nevereat/`)
unusable for it: the crawler would look at `app-works-247.github.io/app-ads.txt`,
which this repository does not control. **A custom domain is required.**

1. Point the domain's DNS at GitHub Pages.
2. Settings -> Pages -> Custom domain. GitHub then commits a `CNAME` file into
   `docs/` by itself, so do not hand-write one.
3. Put the **same** domain in App Store Connect as the app's marketing/support
   URL. It has to match exactly, `www.` included.
4. Confirm `https://<domain>/app-ads.txt` returns the file as `text/plain`.
5. Wait at least 24h, then check the status in AdMob.

Re-download the Appodeal portion whenever Appodeal changes its demand partners.
