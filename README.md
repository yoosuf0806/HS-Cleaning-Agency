# SparkleClean — Cleaning Services (Melbourne)

A single-page marketing site for **SparkleClean**, a residential & commercial
cleaning business in Melbourne. Built as a plain, dependency-free static site
following the SparkleClean design template — emerald/forest-green palette,
heavy uppercase display headings and a clean body sans.

## Run it

Static site — open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Structure

```
index.html        # the whole site (HTML + inline CSS + a small vanilla-JS block)
images/           # photos
  dining-area.jpg        # used in the hero
  kitchen-cooktop.jpg    # available (not placed by default)
  bedroom.jpg            # available
  bedroom-city-view.jpg  # available
  bathroom.jpg           # available
```

## Sections

Sticky nav · Hero · About / our team · How we work (4 steps) · Services
(2×2) · Service areas (map) · FAQ · Get-a-quote form · Footer.

## Design

- **Fonts:** Archivo (headings, heavy/uppercase) + Inter (body), via Google Fonts.
- **Colours:** emerald green `#15B36A`, forest-green bands `#0B3A2A`, mint
  section backgrounds `#E9F6EF`. All defined as CSS variables on `:root`.
- Hover animations on buttons, step cards, service cards, suburb pills; the
  FAQ accordion and quote-form confirmation are vanilla JS.

As requested, trust badges and stats (Fully Insured / Police Checked /
Satisfaction Guarantee, the "8+ years" badge and the "4.9★" rating card) from
the reference mock are intentionally **omitted**.

## Photos

The hero uses `dining-area.jpg`. The **About** section currently shows a
placeholder (`[Add your crew photo]`) because it calls for a photo of the team
— drop a crew photo into `images/` and swap the placeholder `<div class="about-ph">`
for an `<img>`. The other four photos in `images/` aren't placed by default
(this template only has hero + team photo slots); if you'd like an "Our Work"
gallery to showcase all five, it can be added in the same style.

## Placeholders to replace with real details

- Phone `(03) 9000 1234`, email `hello@sparkleclean.com.au`, `Melbourne, VIC`
- Opening hours (nav/footer/quote section)
- `ABN [00 000 000 000]` (footer)
- Service-areas map is a stylised SVG placeholder — swap for a real Google
  Maps embed if you want an interactive map.
- Social links (`#`) in the footer.

## Wiring up the quote form

The form currently shows a thank-you message only (no backend). To receive
submissions, point `<form id="quote-form">` at a form handler (e.g. Formspree,
Web3Forms, or your own endpoint) and send the fields: `name`, `phone`,
`email`, `suburb`, `service`.
