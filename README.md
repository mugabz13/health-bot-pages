# Health Bot pages

Public static homepage and privacy policy for a personal-use Health Bot tool. The two pages are the homepage URL and the separate privacy-policy URL for the owner’s own Google OAuth branding screen.

This is not a dashboard. The pages do not sign anyone in, do not show health data, and do not change the Google OAuth client, scopes, or branding settings.

Health Bot is not a Google product. Nothing in this repository means Google has verified the app.

## Files

- `index.html` — homepage
- `privacy.html` — privacy policy (a different page from the homepage)
- `styles.css` — shared stylesheet
- `.nojekyll` — tells GitHub Pages to serve these files directly, with no Jekyll build

There is no package install and no build step.

## Free GitHub Pages

GitHub Pages on a public repository is free. Use the default `github.io` address. Do not add a custom domain, do not buy a domain, and do not change billing.

Someone with **admin** access to this repository has to turn Pages on. Publishing uses the default branch, so merge the pages into `main` first. Until that merge, Pages would still be serving the old `main` commit, which does not contain these files.

After the merge:

1. Open this repository on GitHub.
2. Go to **Settings → Pages**. Official guide: [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Set the branch to `main` and the folder to `/ (root)`.
5. Click **Save**.
6. Wait until the Pages deployment finishes. The settings page shows the site URL.

Expected project-site addresses after that deployment succeeds:

- Homepage: `https://mugabz13.github.io/health-bot-pages/`
- Privacy: `https://mugabz13.github.io/health-bot-pages/privacy.html`

Those URLs are different on purpose. Links in the HTML are relative (`index.html`, `privacy.html`, `styles.css`, and same-page `#anchors`), so they keep working when the site is hosted under `/health-bot-pages/`.

Check the live pages yourself before pasting them into any OAuth screen. A settings save that has not finished deploying is not a working URL yet.

## Local check

From this directory:

```bash
python3 -m http.server 8080
```

Open `http://127.0.0.1:8080/` and `http://127.0.0.1:8080/privacy.html`.

To mimic the project-site path, serve a parent folder that contains this directory as `health-bot-pages`, then open `/health-bot-pages/` and `/health-bot-pages/privacy.html`.

## What not to publish

Do not commit secrets, OAuth client IDs or client secrets, token files, health measurements, personal names, or email addresses. The contact line points at the support email already saved on the OAuth branding screen and does not print that address here.
