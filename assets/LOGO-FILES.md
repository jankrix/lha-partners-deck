# Logo files — what's actually in each one

Measured, not assumed. Every file in this folder is a **JPEG** (`hasAlpha: no`), and **a JPEG cannot store transparency**. Three of the four variants are exports that *show* a transparency checkerboard — but the checkerboard is **baked into the pixels**, so dropping one on a slide paints a grey grid onto the background.

Sampled background, per file:

| File | Wordmark | Sampled background | Usable? |
|---|---|---|---|
| `Gemini_Generated_Image_c8xnpic8xnpic8xn.jpeg` | navy | alternating **72 / 147** greys | ✗ checkerboard baked in |
| `Gemini_Generated_Image_c8xnpic8xnpic8xn (1).jpeg` | white | alternating **203 / 255** greys | ✗ checkerboard baked in |
| `Gemini_Generated_Image_c8xnpic8xnpic8xn (2).jpeg` | black | alternating **205 / 255** greys | ✗ checkerboard baked in |
| `Gemini_Generated_Image_tjnq0ztjnq0ztjnq.jpeg` | navy | **99% pure white** (255,255,255) | ✓ solid white, no grid |

## What the deck uses

`lha-logo-white-transparent.png` — a white knockout of the real artwork, because all eight slides are navy and the mark has to be white. Built from `tjnq0ztjnq0ztjnq.jpeg`: cropped tight to the lockup, scaled to **800×738**, every non-white pixel forced to pure white, and the white page feathered out to alpha 0 so it composites on navy with no halo. Embedded in `index.html` as base64 so the deck stays a single file.

`lha-favicon.png` — 180×180 navy tile with the white **emblem only** (not the full lockup: "LHA" plus the descriptor line are unreadable at 16px). A bare white-on-transparent favicon would be invisible in a light browser tab bar, hence the navy tile. Embedded as a data URI in the `<head>`.

`lha-logo-navy-transparent.png` — the same crop in real colours (navy wordmark, amber star), background keyed transparent. For light slides, documents, invoices.

`lha-partners-logo-tight.jpg` / `lha-partners-logo-markonly.jpg` — navy-on-white crops (~50 KB / ~33 KB), kept for a white-slide fallback.

## A note on `gemini-svg.svg`

Not usable as a brand asset. It's a **Gemini reconstruction**, not the real mark: every fill is `#000000` (no navy `#17375E`, no amber `#F59E0B`), the starburst is a straight-line 14-vertex polygon rather than the designed burst with its negative-space star, and "LHA" is a live `<text>` element in Montserrat — which falls back to a system font when the SVG is loaded as an image, since an image-loaded SVG cannot fetch web fonts. Ask whoever drew the mark for a real vector export; it would drop the deck's logo cost from ~47 KB to a couple of KB with no resolution ceiling.

The tight crop is why the deck's logo box is small (134px on the title, 114px on the closing): the original file carried ~22% empty margin on each side, so a much smaller box paints the same size mark.

`lha-partners-logo.jpg` — the original 1408×768 export, kept for reference.

## If you want the transparent or white versions

Those are the ones that would let the logo sit directly on a **navy** slide, and they're the ones that came through broken. Re-export them as **PNG with transparency** (from Gemini, Figma, Illustrator — anything that writes alpha) and drop them here. JPEG will flatten transparency every time, so a `.jpg` can never be the transparent variant.

Two candidates worth asking for:
- **white-on-transparent PNG** — lets the logo sit on the navy slides, which is the stronger look for the bookends.
- **black-on-transparent PNG** — for documents, invoices, and letterheads.
