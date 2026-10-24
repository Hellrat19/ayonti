# Product

<!-- impeccable:product-schema 1 -->

<!-- Source: POLISH-NOTES.md (owner's polish brief, Oct 2026) and the existing index.html. The interview was answered from that brief rather than live; facts marked (inferred) come from the site copy, not the owner. -->

## Platform

web

## Users
Shoppers in Dhaka and across Bangladesh buying bedsheets and Deshi Joypuri unstitched three-piece sets. They are mostly on phones, often on mobile data, and read in Bengali and English. They browse, pick a design, then confirm the order and price with the shop by email or phone.

## Product Purpose
A single-page shop for Ayonti (অয়ন্তী), a small bedsheet and three-piece seller in Mirpur, Dhaka. It shows the collection, collects an order into a cart, and hands the order to the owner by email (mailto) or phone. Ayonti confirms the price, stock and delivery by hand. Success means a visitor sends a complete, correct order.

## Positioning
Authentic, premium-quality bedsheets and Deshi Joypuri three-piece at a reasonable price, from a known local shop (founded 19 Nov 2019, 100% recommend across 32 Facebook reviews).

## Operating Context
- Orders are not taken online. The cart builds an order text, which goes to ayontigallery@gmail.com by mailto, or is copied, or read out by phone to +880 1711-195187.
- Payment: bKash or Nagad (Send Money to personal number 01711-195187, only after Ayonti confirms the total) or cash on delivery.
- Delivery: ৳90 inside Dhaka, ৳150 outside Dhaka.
- Many products have no listed price ("Ask for price"); Ayonti adds it when confirming.

## Capabilities and Constraints
- Static single file (`index.html`) plus `media/`; no build step, no backend.
- Mobile data is expensive: keep payloads lean, especially video.
- Product photos in `media/p/` are the owner's Facebook-post images, and most have text (prices, "4PCs Set", watermarks) baked in. No clean versions exist yet.
- Open decision (owner): the slogan is spelled সাঁধ in the hero, footer and meta tags but সাধ in the About heading. Leave both as they are until the owner confirms.

## Brand Commitments
- Name: Ayonti / অয়ন্তী. Slogan: সাঁধ আর সাধ্যের মিলনমেলা (spelling pending, see above).
- Palette taken from the hero fabric film: rani pink, teal, marigold, blush cream, brand plum `#2a1533`.
- Fonts: Galada (Bengali display), Young Serif (Latin display), Hind Siliguri (body).
- Selvedge-stripe section dividers, the hero fabric film, and the petal motif.
- bKash · Nagad · COD, and the cart → order-by-email/phone flow.

## Evidence on Hand
- Hero film and poster: `media/hf-hero-*`.
- Product photos: `media/p/*-480.webp`, `*-900.webp` (text baked in).
- Fabric swatches: `media/swatch-*.webp`, `media/hf-swatch.webp` (photo crop, does not tile).
- 100% recommend, 32 reviews on Facebook (as stated on the site, inferred).
- No testimonials, press or other figures exist; do not invent them.

## Product Principles
1. Lightweight on mobile data before anything decorative.
2. The order a customer sends must be complete and correct.
3. Polish the existing identity; don't redesign it.
4. Bengali first-class alongside English.

## Accessibility & Inclusion
Respect prefers-reduced-motion: the hero video, parallax and petals must stop. Touch-first: tap targets sized for thumbs.
