# Famous Barber — Website Project

**Student:** Nseketelo Sono (ST10518018) · **Module:** WEDE5020 · **Assignment:** Part 3 — Enhancing Functionality and SEO
**Live site:** https://famous-barber.netlify.app *(replace with your real deployed URL)*
**GitHub repository:** *(add link)*

## Project Overview
Famous Barber is a fictional barbershop in Pretoria (Sunnyside and Hatfield branches). The site lets visitors browse prices, learn about the shop, request an appointment and contact the branches.

## Pages
| Page | Purpose |
|---|---|
| `index.html` | Home: open-now badge, stats, popular prices, posts loaded with fetch, FAQ accordion |
| `about.html` | Tabs (story / mission / vision), team, photo gallery with lightbox |
| `services.html` | Dynamic price list with search, filter, sort and details modal |
| `enquiry.html` | Appointment enquiry form (validation, AJAX, cost and availability response) |
| `contact.html` | Leaflet map, branch tabs, nearest-branch finder, contact form that compiles an email |

## Part 3 Features
**JavaScript (`js/`)**
- `main.js`: mobile nav, scroll-reveal and count-up animations, "open now" badge computed from branch hours, JS-created back-to-top button, accordion, keyboard-accessible tabs, gallery + lightbox (native `<dialog>`, arrow keys), posts loaded from `data/posts.json` with `fetch()`.
- `services.js`: listings built from `data.js`, live search with highlighted matches, category filter, sorting, modal.
- `map.js`: Leaflet + OpenStreetMap map with both branches, fly-to buttons, nearest branch via the Geolocation API.
- `forms.js`: JavaScript validation, error messages, AJAX submit.
- `data.js`: single source of truth for services, branches and email address.

**Forms**
- `enquiry.html`: HTML5 attributes plus JS rules (name, SA phone or email, date not in the past and not Sunday, 300-character counter). On success it shows the cost, duration, branch hours and suggested times for the chosen date.
- `contact.html`: validated fields; the data is compiled into an email (shown in a preview) and a "Send email" button opens it addressed to `bookings@famousbarber.co.za`.
- Submission uses `fetch()`. Set `FORM_ENDPOINT` in `js/data.js` (e.g. a Formspree URL) to POST for real; while empty, an asynchronous request is simulated.

**SEO**
- Keyword research: *barber Pretoria, barbershop Sunnyside, barbershop Hatfield, taper fade, beard trim, hot towel shave, haircut prices.*
- Unique title tags (under 60 characters) and meta descriptions (under 160) per page; canonical URLs; Open Graph tags.
- One `h1` per page with `h2`/`h3` hierarchy; descriptive image file names and alt text; internal links in nav, footer and calls to action.
- JSON-LD `HairSalon` structured data (home and contact); `robots.txt`; `sitemap.xml`; mobile-first responsive layout.
- Page speed: lazy-loaded images with width/height, `defer` scripts, `font-display: swap`, preconnect, cache headers, no frameworks.
- Security: Content-Security-Policy meta tag, `_headers` (X-Frame-Options, nosniff, HSTS, Referrer-Policy, Permissions-Policy), Subresource Integrity on Leaflet, honeypot field against bots, user text inserted with `textContent` (no `innerHTML`).
- Off-page SEO: see the **Backlinks and Off-Page SEO** section below.

## Backlinks and Off-Page SEO
Backlinks are links from other websites to Famous Barber. They are created outside the code, so they are tracked here. Update the **Status** column to "Done" and paste the real URL once each one is live. Screenshots are kept in `screenshots/backlinks/`.

| Source | Type | Link to our site | Status | URL of our listing |
|---|---|---|---|---|
| Google Business Profile: Sunnyside | Local SEO | Website button points to the home page | Planned | *(paste link)* |
| Google Business Profile: Hatfield | Local SEO | Website button points to the home page | Planned | *(paste link)* |
| Facebook page | Social media | Website field and bio link | Planned | *(paste link)* |
| Instagram profile | Social media | Link in bio | Planned | *(paste link)* |
| Yellow Pages South Africa | Directory | Business listing website field | Planned | *(paste link)* |
| Yelp / local Pretoria directory | Directory | Business listing website field | Planned | *(paste link)* |
| Neighbouring business or Pretoria blogger | Partnership | Link to `services.html` | Planned | *(paste link)* |

**Strategy**
- **Local SEO:** each branch has its own Google Business Profile using the exact name, address and phone number shown on `contact.html` and in the site's structured data, so the details match everywhere.
- **Social media:** share gallery photos and the "Latest news and tips" posts with a link back to the matching page.
- **Quality over quantity:** only relevant, genuine sites are used. No paid or spam links, which search engines penalise.
- **Reviews:** customers are asked to leave a Google review after their visit.

### Profile text used for backlinks
**Google Business Profile (one per branch)**
> Famous Barber Sunnyside is a Pretoria barbershop offering fades, tapers, beard trims and hot towel shaves from R50. Walk-ins welcome, or book online. Open Mon–Fri 08:00–18:00 and Sat 08:00–15:00.
> *(Hatfield: Mon–Fri 09:00–19:00, Sat 08:00–15:00.)*

**Facebook "About"**
> Proper cuts at honest prices in Pretoria. Fades, tapers, beard trims and hot towel shaves at our Sunnyside and Hatfield branches. Book your cut online: https://famous-barber.netlify.app

**Instagram bio**
> Barbershop in Pretoria · Sunnyside & Hatfield · Proper cuts, honest prices · Book your cut: https://famous-barber.netlify.app

**Directory listing**
> Famous Barber is a Pretoria barbershop founded in 2024, with branches in Sunnyside (123 Esselen Street) and Hatfield (45 Grosvenor Street). Services include haircuts from R50, beard trims, hot towel shaves and combos. Website: https://famous-barber.netlify.app

**Partner outreach message**
> Hi, I'm from Famous Barber in Sunnyside. We'd love to link to your business from our website if you're happy to link back to ours, as it helps both of us get found locally. Let me know if that works for you.

## Folder Structure
```
index.html about.html services.html enquiry.html contact.html
css/style.css
js/ data.js main.js services.js map.js forms.js
data/posts.json
images/ (4 photos with descriptive names)
robots.txt sitemap.xml _headers README.md
```

## Deployment (Netlify)
1. Push the folder to GitHub. 2. In Netlify choose *Add new site → Import from Git*, pick the repo, leave the build command empty and publish directory as `.`. 3. Copy the live URL, then replace `https://famous-barber.netlify.app` in the pages, `robots.txt` and `sitemap.xml`.

## Changelog
### Part 3
- **v3.0**: Added accordion, tabs, modal, Leaflet map, animations, DOM-built dynamic content, gallery with lightbox, search/filter/sort, JS form validation, AJAX submission, SEO files and security headers (details above).

### Corrections following Part 2 feedback
> Feedback received on Part 2, and what was done about it. *(Student: add any further feedback points below in the same format.)*

- **Feedback: Responsive Design, Adjustment – Navigation Menu (0/5): "No navigation menu adjustments made."**
  The Part 2 pages had no media queries, so the menu stayed a single row at every screen size. **Fix:** the navigation is now mobile-first. Below 48rem (768px) the links are hidden behind a "Menu" button (`.nav-toggle`) that opens a full-width stacked list; the button updates `aria-expanded` and is keyboard accessible. From 48rem upward the toggle disappears and the links sit in a horizontal row. The current page is highlighted with `aria-current="page"`, the header is sticky, and a skip-to-content link was added. Tested at 375px, 768px and 1280px (see `css/style.css`, "header / nav", and `js/main.js`, "mobile nav").

**Other issues I found myself while preparing Part 3:**
- Pages used inline `<style>` blocks, so `css/style.css` was not applied. Replaced with one shared stylesheet linked from every page.
- Image paths used lowercase names but files were capitalised (broken on Netlify/GitHub Pages). Renamed to lowercase, descriptive names.
- README described `srcset` images and a `js/` folder that did not match the files. README rewritten to match.
- Prices were inconsistent between pages (e.g. Taper Fade R60 vs R150, Cut and Dye R200 vs R250). Now taken from one data file; **check these prices are correct.**
- Fixed copy errors: "at and affordable price", unclosed `<p>` on the home page, "Est. 2014" vs 2024.
- Added skip link, `aria` attributes, visible focus states and `prefers-reduced-motion` support.

## References
- MDN Web Docs: `<dialog>`, Fetch API, Geolocation API, IntersectionObserver — https://developer.mozilla.org/
- Leaflet 1.9.4 documentation — https://leafletjs.com/
- OpenStreetMap tile usage — https://www.openstreetmap.org/copyright
- Google Search Central: SEO starter guide, structured data — https://developers.google.com/search
- schema.org `HairSalon` — https://schema.org/HairSalon
- W3C WAI-ARIA Authoring Practices (tabs, accordion) — https://www.w3.org/WAI/ARIA/apg/
- Netlify docs: custom headers — https://docs.netlify.com/
- Images: supplied by the student (Part 2).
