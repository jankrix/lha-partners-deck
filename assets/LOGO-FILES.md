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

`lha-partners-logo-tight.jpg` — built from `tjnq0ztjnq0ztjnq.jpeg`: cropped tight to the artwork (region 1570×1448, plus a 26px pad) and scaled to **700×646**, ~51 KB. It's embedded directly in `index.html` as base64, so the deck stays a single file; this copy is the source.

The tight crop is why the deck's logo box shrank to 118px (title) / 100px (closing): the old file carried ~22% empty margin on each side, this one doesn't, so a much smaller box paints the same size mark.

`lha-partners-logo.jpg` — the original 1408×768 export, kept for reference.

## If you want the transparent or white versions

Those are the ones that would let the logo sit directly on a **navy** slide, and they're the ones that came through broken. Re-export them as **PNG with transparency** (from Gemini, Figma, Illustrator — anything that writes alpha) and drop them here. JPEG will flatten transparency every time, so a `.jpg` can never be the transparent variant.

Two candidates worth asking for:
- **white-on-transparent PNG** — lets the logo sit on the navy slides, which is the stronger look for the bookends.
- **black-on-transparent PNG** — for documents, invoices, and letterheads.
