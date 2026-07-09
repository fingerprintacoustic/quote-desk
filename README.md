# Fingerprint Acoustic — Studio Intake / Quote Desk

Single-file static app. `index.html` is the whole thing — no build step needed.

## Deploy (GitHub Pages, matches your usual setup)

1. **Create the repo**
   - On GitHub, new repo under your `fingerprintacoustic` account/org — suggested name: `quote-desk`.
   - Public repo (required for free GitHub Pages, unless you're on a paid plan).

2. **Push these files**
   ```bash
   cd quote-desk-deploy
   git init
   git add .
   git commit -m "Initial deploy: studio intake quote desk"
   git branch -M main
   git remote add origin https://github.com/fingerprintacoustic/quote-desk.git
   git push -u origin main
   ```

3. **Enable Pages**
   - Repo → Settings → Pages.
   - Source: **GitHub Actions** (the included workflow at `.github/workflows/deploy.yml` handles the rest — it deploys on every push to `main`).
   - First push will kick off the workflow automatically; check the **Actions** tab for progress.

4. **Point the subdomain (Dynadot)**
   - In Dynadot DNS settings for `fingerprintacoustic.com`, add:
     - Type: `CNAME`
     - Subdomain/Host: `quote`
     - Points to: `fingerprintacoustic.github.io`
   - The `CNAME` file already in this repo tells GitHub Pages to serve on `quote.fingerprintacoustic.com` — don't delete it.

5. **Verify**
   - Repo → Settings → Pages should show `quote.fingerprintacoustic.com` as the custom domain, with a checkbox for **Enforce HTTPS** — turn that on once the cert is issued (can take up to ~24h after DNS propagates).

## After that

- Test the flow end to end with a couple of made-up client ideas.
- Live at: `https://quote.fingerprintacoustic.com`
- Confirmed quotes email `info@fingerprintacoustic.com` via a pre-filled `mailto:` link.
