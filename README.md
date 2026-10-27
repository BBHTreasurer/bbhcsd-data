# data.bbhcsd.org

Static site for public data dashboards from the BBHCSD Treasurer's Office, served by GitHub Pages.

## Layout

- `index.html` : landing page that lists the dashboards
- `value/index.html` : "Exceptional Excellence, Unmatched Value" dashboard (self-contained, no external files)
- `CNAME` : the custom domain (`data.bbhcsd.org`)
- `.nojekyll` : tells GitHub Pages to serve files as-is

## One-time setup

1. Create a public repo (for example `bbhcsd-data`) and upload everything in this folder to the root of the `main` branch.
2. Repo Settings > Pages > Build and deployment: Source "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Same page, Custom domain: `data.bbhcsd.org`. Save. Check "Enforce HTTPS" once the DNS check passes (can take up to an hour).
4. DNS (whoever manages bbhcsd.org): add a CNAME record
   `data  CNAME  <github-username>.github.io`
   Use the GitHub account name that owns the repo, not the repo name.

## Updating a dashboard

Replace `value/index.html` with the new file and commit. The link does not change. GitHub Pages republishes within about a minute.

## Embedding on bbhcsd.org (Finalsite)

Add an embed or custom HTML element with:

```html
<iframe src="https://data.bbhcsd.org/value/" width="100%" height="1700" style="border:0" title="BBHCSD Value Dashboard" loading="lazy"></iframe>
<p><a href="https://data.bbhcsd.org/value/" target="_blank" rel="noopener">Open the dashboard full screen</a></p>
```

## Adding another dashboard later

Make a new folder (for example `staffing/`) with its own `index.html`, then add a card for it on the landing page.
