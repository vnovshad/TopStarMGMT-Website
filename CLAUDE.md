# CLAUDE.md — Frontend Website Rules

---

## Project Overview — TopStar MGMT
This is the website for **TopStar MGMT**, an OnlyFans creator management agency.
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
- JSON-LD Organization schema + FAQPage schema in `<head>`
- Heading structure follows client's SEO advisor PDF exactly

## Key CSS Notes
- CSS custom property for pink: `var(--hot-pink)` = `#FF00A8`
- Mobile breakpoint: `@media (max-width: 640px)`
- All mobile-only changes go inside that media query
- Display headings use `clamp(2.2rem, 9vw, [desktop-max])` for responsive sizing

---

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

## Reference Images
- If a reference image is provided: match layout, spacing, typography, and color exactly. Swap in placeholder content (images via `https://placehold.co/`, generic copy). Do not improve or add to the design.
- If no reference image: design from scratch with high craft (see guardrails below).
- Screenshot your output, compare against reference, fix mismatches, re-screenshot. Do at least 2 comparison rounds. Stop only when no visible differences remain or user says so.

## Local Server
- **Always serve on localhost** — never screenshot a `file:///` URL.
- Start the dev server: `node serve.mjs` (serves the project root at `http://localhost:3000`)
- `serve.mjs` lives in the project root. Start it in the background before taking any screenshots.
- If the server is already running, do not start a second instance.

## Screenshot Workflow
- Puppeteer is installed at `C:/Users/nateh/AppData/Local/Temp/puppeteer-test/`. Chrome cache is at `C:/Users/nateh/.cache/puppeteer/`.
- **Always screenshot from localhost:** `node screenshot.mjs http://localhost:3000`
- Screenshots are saved automatically to `./temporary screenshots/screenshot-N.png` (auto-incremented, never overwritten).
- Optional label suffix: `node screenshot.mjs http://localhost:3000 label` → saves as `screenshot-N-label.png`
- `screenshot.mjs` lives in the project root. Use it as-is.
- After screenshotting, read the PNG from `temporary screenshots/` with the Read tool — Claude can see and analyze the image directly.
- When comparing, be specific: "heading is 32px but reference shows ~24px", "card gap is 16px but should be 24px"
- Check: spacing/padding, font size/weight/line-height, colors (exact hex), alignment, border-radius, shadows, image sizing

## Output Defaults
- Single `index.html` file, all styles inline, unless user says otherwise
- Tailwind CSS via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Placeholder images: `https://placehold.co/WIDTHxHEIGHT`
- Mobile-first responsive

## Brand Assets
- Always check the `brand_assets/` folder before designing. It may contain logos, color guides, style guides, or images.
- If assets exist there, use them. Do not use placeholders where real assets are available.
- If a logo is present, use it. If a color palette is defined, use those exact values — do not invent brand colors.

## Anti-Generic Guardrails
- **Colors:** Never use default Tailwind palette (indigo-500, blue-600, etc.). Pick a custom brand color and derive from it.
- **Shadows:** Never use flat `shadow-md`. Use layered, color-tinted shadows with low opacity.
- **Typography:** Never use the same font for headings and body. Pair a display/serif with a clean sans. Apply tight tracking (`-0.03em`) on large headings, generous line-height (`1.7`) on body.
- **Gradients:** Layer multiple radial gradients. Add grain/texture via SVG noise filter for depth.
- **Animations:** Only animate `transform` and `opacity`. Never `transition-all`. Use spring-style easing.
- **Interactive states:** Every clickable element needs hover, focus-visible, and active states. No exceptions.
- **Images:** Add a gradient overlay (`bg-gradient-to-t from-black/60`) and a color treatment layer with `mix-blend-multiply`.
- **Spacing:** Use intentional, consistent spacing tokens — not random Tailwind steps.
- **Depth:** Surfaces should have a layering system (base → elevated → floating), not all sit at the same z-plane.

## Hard Rules
- Do not add sections, features, or content not in the reference
- Do not "improve" a reference design — match it
- Do not stop after one screenshot pass
- Do not use `transition-all`
- Do not use default Tailwind blue/indigo as primary color
