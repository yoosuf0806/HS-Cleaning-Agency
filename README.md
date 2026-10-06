# Hussain Projects Ltd — Cleaning Services website

A single-page marketing site for Hussain Projects Ltd (residential &
commercial cleaning across Watford & Hertfordshire). Built as a plain,
dependency-free static site that reproduces the original design reference
exactly — fonts, colours, SVG graphics and animations — with the real
portfolio photos added.

## Run it

It's a static site, so just open `index.html` in a browser, or serve the
folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Structure

```
index.html        # the whole site (HTML + inline CSS + a small vanilla-JS block)
images/           # portfolio photos
  dining-area.jpg
  kitchen-cooktop.jpg
  bedroom.jpg
  bedroom-city-view.jpg
  bathroom.jpg
```

## Sections

Nav · Hero · Working-standards banner · About · How we work · Services
(residential + commercial) · **Our Work** (portfolio gallery) · Service areas
· FAQ · Get-a-quote form · Footer.

## What's interactive

- **FAQ accordion** — one panel open at a time (CSS + JS), matching the
  original behaviour.
- **Quote form** — client-side only; on submit it shows the "request
  received" confirmation. There is no backend wired up yet, so no email is
  actually sent (see below).
- **Portfolio lightbox** — click any photo in *Our Work* to view it larger;
  close with the ✕, by clicking the backdrop, or with `Esc`.
- All hover animations (buttons, service cards, FAQ rows, area pills, gallery
  cards) are preserved from the original design.

## Photos

The five photos in `images/` are shown in the **Our Work** gallery, and
`dining-area.jpg` also appears in the **About** section. To swap or add
photos, drop files into `images/` and update the matching `<img src=...>` /
`data-full=...` references in `index.html`.

## Placeholders still to fill in

These were left as placeholders in the original reference and are intentionally
kept so real business details can be added:

- `[X]+` years badge (About section)
- `[Your hours]` (footer opening hours — Mon–Fri / Sat / Sun)
- `Company No. [00000000]` (footer)

## Wiring up the quote form

The form currently just shows a thank-you message. To actually receive
submissions, point the `<form id="quote-form">` at a form handler (e.g. your
own endpoint, Formspree, or an email service) and send the fields: `name`,
`phone`, `email`, `area`, `service`.
