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
  dining-area.jpg        # hero + gallery
  living-room.jpg        # gallery
  kitchen-cooktop.jpg    # gallery
  bedroom.jpg            # gallery
  bedroom-city-view.jpg  # gallery
  bedroom-two.jpg        # gallery
  bathroom.jpg           # gallery
```

## Sections

Sticky nav · Hero · About / our team · How we work (4 steps) · Services
(2×2) · **Our work** (portfolio gallery) · Service areas (map) · FAQ ·
Get-a-quote form · Footer.

## Design

- **Fonts:** Archivo (headings, heavy/uppercase) + Inter (body), via Google Fonts.
- **Colours:** emerald green `#15B36A`, forest-green bands `#0B3A2A`, mint
  section backgrounds `#E9F6EF`. All defined as CSS variables on `:root`.
- Hover animations on buttons, step/service/gallery cards and suburb pills; the
  FAQ accordion, quote-form confirmation and photo lightbox are vanilla JS.

As requested, trust badges and stats (Fully Insured / Police Checked /
Satisfaction Guarantee, the "8+ years" badge and the "4.9★" rating card) from
the reference mock are intentionally **omitted**.

## WhatsApp contact

The site prompts visitors to request information on WhatsApp for an instant
reply, via: a nav button, a hero button, a callout + contact line in the quote
section, a footer link, and an **always-visible floating button** (bottom
right). Every WhatsApp link opens `wa.me/94769970226` with a pre-filled
message.

> **The WhatsApp number is a placeholder.** `+94 76 997 0226`
> (`wa.me/94769970226`) is a dummy. To change it, search `index.html` for
> `94769970226` (the `wa.me` links) and `+94 76 997 0226` (the displayed
> number) and replace both with the real international number (country code,
> no `+`, no leading `0`).

## Scroll animations

Sections and cards fade/slide in as they enter the viewport
(`IntersectionObserver`), the hero headline's underline draws in, the hero
photo gently floats, and the map marker pulses. All of this respects
`prefers-reduced-motion` (motion is disabled for visitors who ask for reduced
motion) and degrades gracefully without JavaScript.

## Photos

The hero and the **Our work** gallery (7 photos) use the images in `images/`.
Tap any gallery photo (or the hero photo) to open it in a lightbox. The
**About** section still shows a placeholder (`[Add your crew photo]`) because
it calls for a photo of the team — drop a crew photo into `images/` and swap
the placeholder `<div class="about-ph">` for an `<img>`.

## Placeholders to replace with real details

- **WhatsApp number** `94769970226` / `+94 76 997 0226` (dummy — see above)
- Email `hello@sparkleclean.com.au`, `Melbourne, VIC`
- Opening hours (footer/quote section)
- `ABN [00 000 000 000]` (footer)
- Service-areas map is a stylised SVG placeholder — swap for a real Google
  Maps embed if you want an interactive map.
- Facebook / Instagram links (`#`) in the footer.

## Wiring up the quote form

The form currently shows a thank-you message only (no backend). To receive
submissions, point `<form id="quote-form">` at a form handler (e.g. Formspree,
Web3Forms, or your own endpoint) and send the fields: `name`, `phone`,
`email`, `suburb`, `service`.
