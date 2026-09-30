# LHA Partners — Pitch Deck

Interactive single-file presentation deck for **LHA Partners** (Consultants | Advisory | Agency).

**Live:** https://jankrix.github.io/lha-partners-deck/

## What's here

| Path | What it is |
|---|---|
| `index.html` | The whole deck — one self-contained file (Reveal.js from CDN, logo embedded as base64, custom CSS) |
| `assets/lha-logo-white-transparent.png` | **Used in the deck** — white knockout, transparent, for the navy slides |
| `assets/lha-favicon.png` | Favicon — white emblem on a navy tile (a bare white mark would vanish in a light tab bar) |
| `assets/lha-logo-navy-transparent.png` | Full-colour mark, transparent — for light slides and documents |
| `assets/LOGO-FILES.md` | What's actually inside each logo file, measured — read before using any of them |

No build step, no dependencies to install. Open `index.html` in a browser and it runs.

## Presenting

| Key | Does |
|---|---|
| `→` `←` / `Space` | Next / previous slide |
| `F` | Fullscreen |
| `Esc` `O` | Slide overview |
| `S` | Speaker notes window |

**Export to PDF:** open `index.html?print-pdf` in Chrome, then print to PDF (landscape, no margins, background graphics on).

## The deck

8 slides: title → the growth ceiling → the three-musketeers origin → services → three founder bios → closing CTA.

Palette: navy `#0F2041`, amber `#F59E0B`, slate `#475569`, white. Type: Montserrat headings, Roboto body.

## Editing

Everything lives in `index.html`: slide markup in `<div class="slides">`, styling in the `<style>` block at the top. **Theme.** All eight slides are navy. The logo is a white-on-transparent PNG, so it sits straight on the navy with no card and no white plate — the earlier white bookends existed only because the logo asset had a white background baked into it. Colours run on semantic tokens in `:root` — `--ink`, `--body`, `--muted`, `--panel-bg`, `--panel-br`, `--rule`, `--accent-ink` — and the `.slide-light` class flips the whole set (plus the Reveal tokens) to white: `<section class="slide-light" data-background-color="#FFFFFF">` for a white slide, plain `<section>` for navy.

**Amber text vs amber shapes.** On the white slides, amber *text* is darkened to `#B45309`, because brand amber on white is only 2.1:1 — below the 3:1 that even large display text needs. Amber *shapes* (rules, borders, the logo's star) stay at full `#F59E0B`.

Each bio slide is a two-column `.bio` block — left column is the identity plus `.stat` rows, right column is `.bullets` plus a `.bio-foot` history line.

## Before you send this to anyone

- `hello@lhapartners.com` on the closing slide is a **placeholder** — swap in a live inbox, or make sure the domain and mailbox exist.
- Founder metrics are drawn from the founders' CVs. Confirm anything you would not want to defend in a room.
