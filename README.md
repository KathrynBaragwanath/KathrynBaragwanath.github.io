# kathrynbaragwanath.com

Personal academic website. Plain HTML/CSS — no build step, no framework.

## Structure

- `index.html` — About (homepage)
- `research.html` — Publications and working papers
- `teaching.html` — Courses
- `style.css` — All styling (accent color is set in the `:root` block at the top)
- `assets/` — Photo, CV PDF, syllabi, paper appendix
- `CNAME` — Tells GitHub Pages to serve the site at kathrynbaragwanath.com

## How to update the site

1. Edit the HTML files (e.g. add a paper to `research.html` by copying an existing `<div class="paper">…</div>` block).
2. To update the CV, replace `assets/CV_Baragwanath.pdf` with the new file (same filename).
3. Commit and push — GitHub Pages redeploys automatically in ~1 minute:

```bash
git add -A && git commit -m "Update site" && git push
```

## One-time setup: publishing on GitHub Pages

1. Create a GitHub account (if needed), then create a new **public** repository
   named `<username>.github.io` (or any name, e.g. `website`).
2. From this folder:

```bash
git init
git add -A
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

3. On GitHub: repo → Settings → Pages → Source: "Deploy from a branch",
   Branch: `main`, folder `/ (root)`. Save.
4. Still in Settings → Pages, under "Custom domain" enter
   `kathrynbaragwanath.com` and tick **Enforce HTTPS** (available once DNS
   propagates).

## One-time setup: pointing the domain at GitHub

At your domain registrar (currently Squarespace Domains), edit DNS records:

- Four **A records** for `@` (the bare domain), one for each IP:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
- One **CNAME record**: host `www` → `<username>.github.io`

Delete any old A/CNAME records that point at Squarespace. DNS changes can
take from a few minutes to a day to propagate. Keep the Squarespace site up
until the new one is live, then cancel the Squarespace website subscription
(keep the **domain** registration!).
