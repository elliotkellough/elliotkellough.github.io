# COLOSSEUM Website

## File Structure
```
/
├── index.html          — Home page
├── about.html          — About page
├── portfolio.html      — Portfolio page
├── contact.html        — Contact page
├── CNAME               — Your domain (for GitHub Pages)
├── css/style.css       — All shared styles
├── js/main.js          — Shared JavaScript
├── images/
│   ├── logo.png        — Main logo
│   ├── logos/          — Client logo images for carousel (see below)
│   └── ...             — Project images/videos
└── projects/
    ├── pvl.html        — The Canadian Whey
    ├── endzn.html      — Dinos × ENDZN
    ├── raw.html        — Junior Cardinals
    ├── endzn2.html     — Create Your Player
    ├── pvl2.html       — The 4X Experiment
    └── qb.html         — QB Motion Launch Course
```

---

## Adding Client Logos to the Carousel

1. Create a folder: `images/logos/`
2. Add logo image files (white PNG with transparent background recommended):
   - `images/logos/purevitalabs.png`
   - `images/logos/endzn.png`
   - `images/logos/rawsports.png`
   - `images/logos/arizonacardinals.png`
   - `images/logos/qbmotion.png`
   - `images/logos/calgarydinos.png`
   - `images/logos/redbull.png`
   - `images/logos/cfl.png`
3. If a logo file is missing, the text name shows as a fallback automatically.

Recommended logo specs: white/light-coloured PNG, transparent background, ~200–300px wide.

---

## Adding Project Media

### Portfolio page (portfolio.html)
Each project entry has a `<!-- ADD PROJECT IMAGE/VIDEO -->` comment inside `.project-visual-inner`.
Replace with:
```html
<img src="images/pvl-cover.jpg" alt="The Canadian Whey">
```
or for a video preview:
```html
<video autoplay muted loop playsinline>
  <source src="images/pvl-preview.mp4" type="video/mp4">
</video>
```

### Individual project pages (projects/*.html)
Each project page has three media areas:

**1. Hero background** — in `.project-hero-visual`:
```html
<img src="../images/pvl-hero.jpg" alt="The Canadian Whey">
```

**2. Video embed** — in `.video-embed-wrap`:
```html
<!-- YouTube -->
<iframe src="https://www.youtube.com/embed/YOUR_ID" allowfullscreen></iframe>

<!-- Vimeo -->
<iframe src="https://player.vimeo.com/video/YOUR_ID" allowfullscreen></iframe>

<!-- Self-hosted -->
<video controls>
  <source src="../images/pvl.mp4" type="video/mp4">
</video>
```

**3. Gallery grid** — replace placeholder `<div class="gallery-item">` blocks:
```html
<div class="gallery-item">
  <img src="../images/pvl-1.jpg" alt="Behind the scenes">
</div>
```
Add as many gallery items as needed; the grid is 3 columns.

---

## GitHub Pages Setup

### Step 1 — Create repository
Name it exactly: `yourusername.github.io` (set to Public)

### Step 2 — Upload files
Upload ALL files and folders maintaining the folder structure.

### Step 3 — Visit your site
`https://yourusername.github.io` (live in 1–2 minutes)

---

## Connect GoDaddy Domain

**CNAME file:** edit to contain only your domain, e.g. `colosseumcreative.ca`

**GitHub Pages:** Settings → Pages → Custom domain → enter domain → Enforce HTTPS

**GoDaddy DNS:**
- Delete existing A records
- Add 4 A records (Name: @):
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153
- Add CNAME: Name: www → Value: yourusername.github.io

Wait 10–30 minutes.

---

## Contact Form (Real Email)

1. Sign up at formspree.io (free)
2. Create a form → get your form ID
3. In `contact.html`, change the submit handler to:
```javascript
const response = await fetch('https://formspree.io/f/YOUR_ID', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name, email, message })
});
```

---

## Update Contact Info

In `contact.html`:
- Email: replace `hello@colosseumcreative.ca`
- Phone: replace `+1 (403) 000-0000`
- Social links: replace all `href="#"` with real URLs

Social links appear in the nav footer on all pages — update in each file, or add them to the JavaScript in `js/main.js` to set them once.
