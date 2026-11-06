# TempleVault Marketing Site - Owner Guide

For the primary administrator. Everything needed to maintain `https://www.templevault.net` day to day.

## What Lives Where

| Item | Location |
|---|---|
| Site files | `github.com/ydar996/templevault-home` (public repo) |
| Hosting | GitHub Pages - free, auto-deploys on every push to `main` |
| Domain | `www.templevault.net` - CNAME record at Namecheap |
| The app | `templevault.net` - separate repo/server, untouched by this site |
| Handoff page | `https://www.templevault.net/dev-handoff-9x4k.html` (unlinked, noindex) |

## Routine Tasks

### Edit a page

1. Edit the HTML file (`index.html`, `features.html`, `pricing.html`, `about.html`) - locally or directly on GitHub (pencil icon).
2. Commit to `main`. The site republishes within about a minute.
3. Check the live page after publishing.

### Add a new page

1. Create `newpage.html` - copy the header/footer from an existing page.
2. Give it a unique `<title>`, `<meta name="description">`, `<link rel="canonical">`, and OG tags.
3. Add it to `sitemap.xml` (new `<url>` entry).
4. Link it from the nav/footer where appropriate.

### Add or remove a developer

- **Add:** repo Settings → Collaborators → Add people → enter their GitHub username. They get push access to this repo only.
- **Remove:** Settings → Collaborators → Remove. Instant - they can no longer change the site.
- Nobody else can change the site. Only collaborators you approve can push.

## Things That Must Not Break

- `CNAME` file at repo root - deleting it unlinks the custom domain.
- Sign in links: `https://templevault.net/login`
- Get Started links: `https://templevault.net/register`
- `sitemap.xml` and `robots.txt` at site root.
- Per-page unique title/description/canonical - never copy-paste across pages.

## DNS (Namecheap)

- `www` → CNAME → `ydar996.github.io` (the one record you added).
- The apex `templevault.net` records belong to the app - do not touch them.
- Domain renewals stay in your Namecheap account as usual.

## SEO Checklist

- [x] HTTPS via GitHub Pages (auto-provisioned)
- [x] `sitemap.xml` + `robots.txt`
- [ ] Verify the domain in **Google Search Console** (search.google.com/search-console) - URL-prefix property `https://www.templevault.net`, then submit `https://www.templevault.net/sitemap.xml`
- [ ] Optional: Bing Webmaster Tools - same sitemap
- [ ] Keep content fresh - Google rewards real, updated copy over time

## If Something Breaks

- **Site down but repo fine:** check repo Settings → Pages - it should show `Your site is live at https://www.templevault.net`.
- **404 after DNS changes:** re-add `www.templevault.net` under Settings → Pages → Custom domain (or re-commit the `CNAME` file).
- **App links broken:** the app itself may be down - check `https://templevault.net/login` directly. The marketing site has no dependency on the app.
