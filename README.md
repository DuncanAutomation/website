# duncan-automation.com — static site

Plain HTML/CSS, ready for GitHub Pages. No build step, no dependencies beyond a Google Fonts link.

## Files
- `index.html` — DAXL Excel Spreadsheet Module (home page)
- `ignition.html` — Ignition by Inductive Automation
- `about.html` — Company overview
- `contact.html` — Contact info + form
- `style.css` — shared stylesheet

## Two things to finish before you publish

1. **Email address** — the old site obfuscated your email via Weebly/Cloudflare,
   so the plaintext address wasn't recoverable from the page. Search-and-replace
   `REPLACE_WITH_YOUR_EMAIL@duncan-automation.com` in `contact.html` with your
   real address (it appears twice).

2. **Contact form backend** — GitHub Pages only serves static files, it can't
   process form submissions. The form currently uses a `mailto:` action, which
   works with zero setup but opens the visitor's email client rather than
   submitting silently. If you'd rather have a normal "it just works" form,
   sign up free at [formspree.io](https://formspree.io) or
   [getform.io](https://getform.io) and swap the `<form action=...>` in
   `contact.html` for the endpoint they give you.

3. **Logo** — the old logo image lived on Weebly's CDN, so I used a simple
   text/mark treatment ("DA") in the header instead of pulling that file.
   Drop your own logo file into an `assets/` folder and swap the `.mark` span
   in each page's header for an `<img>` tag if you'd like your actual logo back.

## Publishing on GitHub Pages

1. Create a repo (e.g. `duncan-automation.github.io` for a user/org site, or
   any name for a project site).
2. Push these files to the repo root (or a `docs/` folder).
3. In the repo's **Settings → Pages**, set the source branch (and `/docs`
   folder if used).
4. If you're keeping the `duncan-automation.com` domain, add a `CNAME` file
   to the repo root containing just:
   ```
   www.duncan-automation.com
   ```
   and point your domain's DNS (a CNAME record for `www`, and the four GitHub
   Pages A records for the apex domain) at GitHub Pages per
   [GitHub's custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
