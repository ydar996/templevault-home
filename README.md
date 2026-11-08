# TempleVault Marketing Site

Static marketing site for TempleVault, hosted on **GitHub Pages** at `https://www.templevault.net`.

This is intentionally a **plain HTML/CSS static site** - no build step, no framework. Push to `main` and GitHub Pages publishes automatically.

## Structure

- `index.html` - home
- `features.html` - feature detail
- `pricing.html` - redirects to `https://templevault.net/features` (country picker + localized pricing in the app)
- `about.html` - about
- `styles.css` - shared styles
- `sitemap.xml` + `robots.txt` - SEO plumbing (update sitemap if pages are added/renamed)
- `CNAME` - tells GitHub Pages the custom domain (`www.templevault.net`)

## App links (keep these working)

Every page links back to the app:

- Sign in: `https://templevault.net/login`
- Pricing: `https://templevault.net/features` (app country picker, localized pricing)
- Get Started / Create an Account: `https://templevault.net/register`

Keep at least one obvious path to each on every page (nav + footer currently).

## SEO notes for the redesign

- Each page has `<title>`, `<meta name="description">`, `<link rel="canonical">`, and Open Graph tags - keep per-page titles/descriptions unique.
- `sitemap.xml` and `robots.txt` must stay at the site root.
- Keep semantic headings (one `<h1>` per page) and add alt text to images.
- The JSON-LD `SoftwareApplication` block in `index.html` helps search engines - update rather than remove.

## DNS (one-time)

`www` CNAME record at the domain registrar points to `ydar996.github.io`. HTTPS is provisioned by GitHub automatically once DNS resolves.

## Dev preview

Open `index.html` in a browser, or run `python -m http.server` in this folder.
