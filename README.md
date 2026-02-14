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

### Custom domain: clawdeploy.macropulse.co

The repo is configured to serve at **https://clawdeploy.macropulse.co**.

1. **GitHub**  
   - **Settings** → **Pages** → **Custom domain**  
   - Enter `clawdeploy.macropulse.co` and save.  
   - Enable **Enforce HTTPS** once the DNS check is green.

2. **DNS** (where `macropulse.co` is managed, e.g. Cloudflare, Route53, etc.)  
   Add a **CNAME** record:

   | Type | Name / Host        | Value / Target       |
   |------|--------------------|----------------------|
   | CNAME | `clawdeploy`       | `macropulse.github.io` |

   - **Name**: `clawdeploy` (for zone `macropulse.co`) so the full name is `clawdeploy.macropulse.co`.  
   - **Target**: `macropulse.github.io` (no `https://`, no trailing dot unless your provider requires it).

3. Wait for DNS to propagate (often 1–5 minutes; up to 48 hours). Then **Enforce HTTPS** in Pages settings if it wasn’t already enabled.

The `.nojekyll` file tells GitHub Pages to serve the files as-is without Jekyll processing. The `CNAME` file in the repo root tells GitHub which custom domain this site uses.

---

## Multiple product landing pages (macropulse convention)

**Pattern: one subdomain per product** — e.g. `clawdeploy.macropulse.co`, `otherproduct.macropulse.co`.

- One repo per product (e.g. `clawdeploy-landing-page`, `otherproduct-landing-page`).
- Each repo has its own GitHub Pages site and its own custom domain.

### Adding a new product landing page

1. **Create a new repo** (e.g. `otherproduct-landing-page`) and add your static site (e.g. `index.html`).
2. **Add these files in the repo root:**
   - **`.nojekyll`** — empty file (so GitHub doesn’t run Jekyll).
   - **`CNAME`** — single line: your subdomain, e.g. `otherproduct.macropulse.co`.
3. **GitHub:** **Settings** → **Pages** → **Source**: Deploy from branch `main` / root → **Custom domain**: `otherproduct.macropulse.co` → Save → Enforce HTTPS when DNS is green.
4. **DNS** (for `macropulse.co`): Add a **CNAME** record:
   - **Name:** `otherproduct` (or whatever subdomain you chose)
   - **Target:** `macropulse.github.io`

Result: **https://otherproduct.macropulse.co** serves that repo’s content. Repeat for each product.
