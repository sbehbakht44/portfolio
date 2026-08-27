# Sara Behbakht — Portfolio

Personal portfolio, live at **https://sarabehbakhtportfolio.com**.
Static site — no build step, no dependencies. Every page is a single self-contained
HTML file (styles, scripts, and images inlined), hosted on GitHub Pages.

## Structure

```
├── index.html               homepage (typewriter hero + selected work)
├── about.html               bio + hobby photos
├── resume.html              resume preview + PDF download
├── soluna.html              case study 01 — Soluna
├── the-garden.html          case study 02 — The Garden
├── grant-compass.html       case study 03 — Grant Compass
├── project-halo.html        case study 04 — Project Halo
├── sara-behbakht-resume.pdf the downloadable resume
├── garden/                  story artifacts linked from the-garden.html
├── 404.html                 not-found page
├── design-system.html       internal design reference (not linked from the site)
├── CNAME                    custom domain for GitHub Pages
└── .nojekyll                tells Pages to serve files as-is
```

## Deploying (first time)

1. **Create the GitHub repo.** On github.com: New repository → name it
   `portfolio` (or anything) → Public → create it **empty** (no README).

2. **Push this folder:**
   ```bash
   cd path/to/this/folder
   git init -b main
   git add -A
   git commit -m "Launch portfolio"
   git remote add origin https://github.com/YOUR-USERNAME/portfolio.git
   git push -u origin main
   ```

3. **Turn on GitHub Pages.** Repo → Settings → Pages →
   Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
   The site will be live at `https://YOUR-USERNAME.github.io/portfolio/` within a minute or two.

4. **Connect the domain.** You must own `sarabehbakhtportfolio.com`
   (buy it at any registrar — Namecheap, Porkbun, Cloudflare, Google-successor Squarespace, etc.).
   At your registrar's DNS settings add:

   | Type  | Host | Value                    |
   |-------|------|--------------------------|
   | A     | @    | 185.199.108.153          |
   | A     | @    | 185.199.109.153          |
   | A     | @    | 185.199.110.153          |
   | A     | @    | 185.199.111.153          |
   | CNAME | www  | YOUR-USERNAME.github.io  |

5. Back in repo → Settings → Pages → **Custom domain**: enter
   `sarabehbakhtportfolio.com`, save, and once the DNS check passes tick
   **Enforce HTTPS**. (DNS can take from minutes to a few hours to propagate.)

   The `CNAME` file in this repo keeps the domain setting from being lost on
   future pushes — don't delete it.

## Updating the site

Edit the HTML file, then:

```bash
git add -A && git commit -m "Describe the change" && git push
```

Pages redeploys automatically in about a minute.

## Design system

Three typefaces (Newsreader for display, Inter for body/UI, Caveat for captions),
sentence case everywhere, one arrow set (→ ← ↓), one button style. The full spec
lives in `design-system.html`, and every page carries the same `DESIGN SYSTEM`
block at the end of its `<style>` — edit it in one file, mirror to the others.

## Notes

- Case-study pages are large (10–25 MB) because all imagery is inlined as
  data URIs; first load on slow connections will take a few seconds.
- `garden/` filenames are referenced from `the-garden.html` — keep names in sync
  if you replace those files.
