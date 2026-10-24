# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-page shop for Ayonti (অয়ন্তী), a small bedsheet and Joypuri three-piece seller in Mirpur, Dhaka. Everything — HTML, CSS, and JS — lives in `index.html`; assets are in `media/`. No build step, no package manager, no tests, no backend. Not a git repository, so make targeted edits and keep a copy of `index.html` before large changes.

Product facts, brand commitments and open owner decisions are in `PRODUCT.md`; the original polish brief is `POLISH-NOTES.md`. Read them before design work.

## Running it

`.claude/launch.json` defines the `ayonti` preview (`python -m http.server 8123`). Start it with the browser preview tool (`preview_start` name `ayonti`), not Bash. Verify at 390px and 1366px widths (no horizontal scroll).

Design checks: `.claude/skills/impeccable/scripts/impeccable detect index.html` (Windows without `sh`: `impeccable.cmd`). Brand-sanctioned false positives (gradient wordmark, cream ground, selvedge stripes, wrapper padding) are already suppressed in `.impeccable/config.json`.

## Architecture of index.html

- **Line 1** is a generic page-skeleton wrapper (duplicate charset/viewport, a 14px body reset) ahead of the real `<head>` content; the real styles come after it in the second `<style>` block and override it.
- **Design tokens** are CSS custom properties on `:root` (`--rani`, `--teal`, `--gada` text-safe teal, `--gold`, `--plum`, `--night` page cream, `--cotton` text). Several names are legacy from an older dark theme (`--night` is the light page colour); use the tokens, don't rename them. The `footer` element re-scopes these tokens for the plum footer — so a plain `<footer>` anywhere else inherits the plum background; use another element inside cards.
- **Products** are defined only in the `PRODUCTS` object in the inline script. Cards, filters, colour swatches and counts are generated from it. Images are expected at `media/p/<id>-480.webp` and `-900.webp`. `price:null` means "Ask for price".
- **Shop rail** (`#shop`): horizontal scroll-snap carousel with category tabs (`bedsheet` / `dress`), filter panel, arrows and dots, all driven by `state` + `applyShop()`. Category choice persists in `sessionStorage`.
- **Cart and checkout**: cart lives in `localStorage` (`ayonti-cart`), rendered in the `#cart` drawer (inert/aria-hidden when closed, Tab-trapped when open). Checkout validates name, a Bangladeshi mobile number and address, then builds a plain-text order shown in `#order-text` and put into a `mailto:ayontigallery@gmail.com` link. Nothing is sent by the page itself. Delivery is ৳90 inside / ৳150 outside Dhaka; payment is bKash / Nagad (Send Money to 01711-195187 after confirmation) / COD. Keep the order text and mailto body identical.
- **Motion**: scroll parallax runs off `[data-depth]` elements (read-then-write in one rAF; `[data-fill]` layers are clamped to their overscan). The hero video is `preload="none"` and started from JS only after `load`, when in view, and never under reduced motion, Data Saver or 2G. Petals sway around their own `--r` angle. All motion must stop under `prefers-reduced-motion` — CSS animations are wrapped in `no-preference`, and the script checks `reduce.matches`.
- **Reviews section** quotes real Facebook recommendations verbatim (names as first name + initial, no photos). Never invent or reword reviews.

## Constraints

- Polish, don't redesign: keep the rani-pink/teal/marigold/plum palette, Galada + Young Serif + Hind Siliguri, selvedge dividers, and the cart → order-by-email/phone flow.
- Most visitors are on phones over mobile data: keep payloads small and gate heavy media.
- Most product photos in `media/p/` have Facebook-post text (prices, watermarks) baked in; use `hf-hero-poster.webp`, `hf-swatch.webp` or the seamless `swatch-*.webp` tiles where clean imagery is needed. `hf-swatch.webp` is a photo crop and does not tile.
- Slogan spelling is সাঁধ আর সাধ্যের মিলনমেলা (owner confirmed).
