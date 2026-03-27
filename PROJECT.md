# PROJECT.md — TopStar MGMT Website

## Project Overview
**TopStar MGMT** is an OnlyFans creator management agency.
- **Live site:** https://www.topstarmgmt.com
- **GitHub repo:** `vnovshad/TopStarMGMT-Website` (main branch)
- **Hosting:** Vercel — auto-deploys on every `git push origin main`
- **Single file site:** everything is in `index.html` — all CSS inline, no separate stylesheet
- **Always push to GitHub after every edit**

## Credentials (do not modify these)
- **Formspree endpoint:** `https://formspree.io/f/mykbyzyj` (sends to `vic.nova@topstarmgmt.com`)
- **Instagram:** @topstarmgmt

## Brand
- **Primary accent:** Hot Pink `#FF00A8`
- **Light mode only** — dark mode is permanently disabled
- **Fonts:** Cormorant Garamond (headings), DM Sans (body/UI), Oswald (ticker only)
- **Logo:** `brand_assets/NEW LOGO.jpeg` — used in nav and footer
- **Favicon:** `favicon.png` in project root (pink star cropped from logo)

## Site Structure (top → bottom)
1. **Nav** — fixed white bar, logo left, hamburger right on mobile
2. **Million Dollar Section** — "Become a Million Dollar Creator with TopStar MGMT", 3 creator photos, CTA button
3. **Hero** — "Your Star Rises Here", subtext, Apply Now button, pink grid background
4. **Ticker** — "UNLOCK YOUR POTENTIAL" scrolling marquee (Oswald)
5. **Testimonials** — video embeds ("Hear it from our creators")
6. **Services** — 6 cards with H2 headings: OnlyFans Account Management, Content Strategy, Messaging & Fan Monetization, Brand Development, Social Media Management, OnlyFans Promotion Strategies
7. **Stats** — 200+ Creators, $2M+ Revenue, 0% Upfront, 24/7 Support
8. **Process** — 4 steps: Apply, Consultation, Onboarding, Growth
9. **Photo Carousel** — scrolling creator photos (media/ folder)
10. **FAQ** — H2: "OnlyFans Agency Management FAQs", 11 accordion questions (all H3)
11. **Contact Form** — "Are you ready to work with TopStar MGMT?", social proof strip, Formspree form (First Name, Last Name, Email, Phone with country dropdown, Instagram @, Telegram @, Message)
12. **Footer** — logo, nav links, Apply Now, copyright

## SEO (already implemented — do not duplicate)
- Visually hidden H1: "OnlyFans Management Agency for Creators"
- Title, meta description, Open Graph, Twitter card all set
- JSON-LD Organization schema (sameAs: instagram.com/topstarmgmt) + FAQPage schema in `<head>`
- Heading structure follows client's SEO advisor PDF exactly

## Key CSS Notes
- CSS custom property for pink: `var(--hot-pink)` = `#FF00A8`
- Mobile breakpoint: `@media (max-width: 640px)`
- All mobile-only changes go inside that media query
- Display headings use `clamp(2.2rem, 9vw, [desktop-max])` for responsive sizing
