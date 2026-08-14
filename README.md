# michaelachodounska.github.io

Static rebuild of the Google Sites page, ready for GitHub Pages.

## What's here

```
site/
├── index.html        homepage
├── research.html      publications, theses & presentations
├── portfolio.html      design/typography page
├── css/style.css        shared styles
└── assets/            put your three photos + CV here (required — see below)
```

No build step, no dependencies — it's plain HTML/CSS. Open `index.html`
directly in a browser to preview it locally.

Colors and fonts are pulled from your actual published site: the
green (`#274e13`), Lexend for headings, Montserrat for body text.

## 1. Add your images and CV (do this before you take the Google Site down)

The site now points to local files instead of Google's servers, so
once you unpublish the Google Site / stop sharing the Drive folder,
those old links will stop working. Grab everything now, while it's
still live:

**Photos** — visit your current Google Site and right-click each
photo → "Save image as" (or open it in a new tab and save from
there). Save into this repo's `assets/` folder using these exact
names:
- `assets/homepage-1.jpg` — the wide photo near the top of the
  homepage
- `assets/homepage-2.jpg` — the second homepage photo, near the
  contact line
- `assets/portfolio-1.jpg` — the photo on the portfolio page

**CV** — every page's nav links to `assets/cv.pdf`. Open your
current Google Drive CV link, download the PDF, and save it into
`assets/` as exactly `cv.pdf`. If you'd rather use a different
filename or keep it as e.g. `.docx`, just update the `href=` on the
"curriculum vitae" link in each of the three HTML files to match.

If you'd rather use different filenames for the photos, just update
the matching `src=` in `index.html` / `portfolio.html` to match.

The research page has no image, so nothing extra needed there.

## 2. Put it on GitHub

If you've never done this before, here's the whole path:

1. **Create the repo.** On github.com, click **New repository**.
   - If you want the site at `https://<yourusername>.github.io`,
     name the repo exactly `<yourusername>.github.io`.
   - If you're fine with it living at
     `https://<yourusername>.github.io/<reponame>`, any name works
     (e.g. `homepage`).
   - Leave it public, don't add a README (you already have one).

2. **Push this folder to it.** In a terminal, `cd` into this `site`
   folder, then:

   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<yourusername>/<reponame>.git
   git push -u origin main
   ```

   (No git installed, or prefer a GUI? GitHub Desktop does the same
   thing with buttons instead of commands — download it, "Add local
   repository," point it at this folder, then "Publish.")

3. **Turn on Pages.** In the repo on GitHub: **Settings → Pages** →
   under "Build and deployment," set **Source** to *Deploy from a
   branch*, branch **main**, folder **/ (root)** → **Save**.

4. **Wait a minute, then visit it.** GitHub will show the live URL
   at the top of that same Pages settings screen once it's built
   (usually under a minute).

## 3. Optional: custom domain

If you'd rather it live at your own domain instead of a
`github.io` address, add a `CNAME` file to the repo root containing
just your domain, then point your domain's DNS at GitHub's Pages
servers — GitHub's own guide walks through the DNS records:
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## Notes

- The portfolio PDF link still points to Google Drive (the "portfolio (2025)" link on the portfolio page). If you'd rather host that in the repo too, drop it in `assets/` and update the `href` in `portfolio.html` to the local path — same approach as the CV.
- Colors, fonts, and layout live entirely in `css/style.css` — safe
  to tweak without touching the HTML.
