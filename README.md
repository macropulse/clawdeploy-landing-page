# ClawDeploy Landing Page

Landing page for [ClawDeploy](https://clawdeploy.com) – The DevOps Protocol for AI Agents.

## GitHub Pages

This site is set up to be published with [GitHub Pages](https://pages.github.com/).

### Enable the site

1. Push this repo to GitHub (if not already):  
   `git push -u origin main`
2. Open the repo on GitHub: **https://github.com/macropulse/clawdeploy-landing-page**
3. Go to **Settings** → **Pages** (left sidebar).
4. Under **Build and deployment**:
   - **Source**: Deploy from a branch
   - **Branch**: `main` (or your default branch)
   - **Folder**: `/ (root)`
5. Click **Save**. The site will be available at:
   - **https://macropulse.github.io/clawdeploy-landing-page/**

Updates to `main` are deployed automatically; it may take 1–2 minutes.

### Custom domain (optional)

To use a custom domain (e.g. `clawdeploy.com`):

1. In **Settings** → **Pages**, enter the domain in **Custom domain** and save.
2. In your DNS provider, add a CNAME record pointing that domain to `macropulse.github.io` (or the A records GitHub shows in the Pages settings).

The `.nojekyll` file in the repo tells GitHub Pages to serve the files as-is without Jekyll processing.
