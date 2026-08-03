# Suhail Ismail Kunju — Portfolio

A single-file portfolio site (`index.html`) — no build step, no dependencies beyond Google Fonts.

## Deploy to GitHub Pages

1. Create a new repository on GitHub, e.g. `sikunju/portfolio` (or `sikunju.github.io` if you want it at the root domain).
2. Upload `index.html` to the root of that repository (drag-and-drop on GitHub, or via git):
   ```
   git init
   git add index.html
   git commit -m "Add portfolio site"
   git branch -M main
   git remote add origin https://github.com/sikunju/portfolio.git
   git push -u origin main
   ```
3. On GitHub: go to the repo → **Settings** → **Pages**.
4. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`, then **Save**.
5. Wait 1–2 minutes. Your site will be live at:
   - `https://sikunju.github.io/portfolio/` (if repo is named `portfolio`), or
   - `https://sikunju.github.io/` (if the repo is named exactly `sikunju.github.io`)

That's it — no further configuration needed.

## Updating content automatically (admin.html)

A second file, `admin.html`, is included — a small private tool that lets you add a new **project**, **experience entry**, or **certification** through a form, and it publishes the change straight to your live site (no code editing required).

**One-time setup:**
1. Upload `admin.html` to the same repo, next to `index.html`.
2. Create a GitHub token at [github.com/settings/tokens?type=beta](https://github.com/settings/tokens?type=beta) → "Fine-grained token" → give it access to only this one repository → permission: **Contents: Read and write**.
3. Open `admin.html` in your browser (either locally, or at `https://sikunju.github.io/<repo>/admin.html` once deployed), expand **Connection settings**, and fill in:
   - GitHub user: `sikunju`
   - Repository: your repo name
   - Branch: `main`
   - File path: `index.html`
   - Access token: the token you just created
4. Click **Save settings**, then **Test connection** to confirm it works.

**To publish a new project, job, or cert:** just fill in the form on that tab and click Publish. It updates `index.html` in your repo directly, which triggers GitHub Pages to redeploy automatically within a minute or two.

⚠️ **Keep the `admin.html` link private** — don't share it or link to it from your public site. Your token is stored only in that browser's local storage and is used only to talk directly to GitHub's API, but anyone who opens that page on your device (or knows the URL and has the token saved there) could publish changes.

