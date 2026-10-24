# Ayonti (অয়ন্তী) — polish brief

Business: bedsheets and Deshi Joypuri unstitched three-piece, Mirpur, Dhaka. Customers are mostly on phones, often on mobile data, reading in Bengali and English.

Keep: the identity. Rani-pink / teal / marigold / plum palette taken from the hero fabric film, Galada + Young Serif + Hind Siliguri, the selvedge stripe dividers, the cart → order-by-email/phone flow, bKash · Nagad · COD. This is a polish pass, not a redesign.

## Issues found in an audit (Oct 2026)

1. **Product photos carry Facebook-post text** (prices, "4PCs Set", watermarks) baked into the image. Worst in the About collage, which shows the cherry-blossom photo with "Price =1,180/-". Swap the About collage to photos without text, or crop the text out.
2. **Mobile hero buttons wrap badly**: at 390px the "Three-piece" button drops onto its own line. Buy now full width, then Bedsheets + Three-piece side by side.
3. **Trust band background shows tile seams**: `media/hf-swatch.webp` repeats as a 300px tile and the edges are visible as squares.
4. **Favicon uses an old palette**: `favicon.svg` background is navy `#0b0d4a`, not the brand plum `#2a1533`.
5. **Leftover CSS from an earlier dark theme**: `.media figcaption` (navy background), `.colors i` (cream border) and other unused rules.
6. **Product cards are heavy**: every card has two large pill buttons (Buy now + Add to cart), so the shop rail is a wall of dark pills.
7. **Payment cell headline** "bKash · Nagad · Cash on delivery" wraps awkwardly at desktop width.
8. **Hero video uses preload="auto"** (1080p is 3.8 MB) — costly on Bangladeshi mobile data.
9. **Check with the owner**: the slogan is spelled সাঁধ in the hero, footer and meta tags but সাধ in the About heading. Confirm which is intended before changing either.

## Check after changes
- 390px and 1366px widths, no horizontal scroll.
- Cart → checkout → "Send this order" still works; order text and mailto body correct.
- prefers-reduced-motion still stops the video, parallax and petals.
