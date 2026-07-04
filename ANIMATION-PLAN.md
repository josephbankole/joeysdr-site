# joeysdr.com animation pass - work plan (ON HOLD: founder 2026-07-04, "no demand".
# Execute only on an explicit founder go, and LAST after thearchv.ca's pass.)

Analyst-ruled scope. Self-contained; any model can execute cold.

## Read first
index.html (single file: styles inline in <style>, dark navy #0B111E + orange
#FF8A3D + mono labels, Space Grotesk/Inter/JetBrains Mono), demo/index.html (already
animated; do not touch). Deploys to GitHub Pages on push to main.

## Positioning law (overrides any design instinct)
Founder-led honesty. There are NO client testimonials and NO fake-shaped proof:
no testimonial carousel, no invented logos, no metric counters for numbers we do
not have. The proof section's founder-direct copy ("pilots run one at a time,
verified numbers to follow") is deliberate and stays. A marquee is allowed ONLY if
it shows real Joey product UI (screenshots of the actual dashboard in
consultancy/joey/demo/dashboard.html rendered with real demo data, clearly framed
as the product, not as client results).

## The moves (in build order)
1. Floating bottom CTA pill: "Book a pilot call" ->
   https://calendly.com/josephbankole/30min?utm_source=joeysdr.com&utm_medium=site&utm_content=pill
   with onclick posthog capture `calendly_click` {site:'joeysdr.com', location:'pill'}.
   Appears after ~600px scroll, hides when the hero CTA or the footer/ctaband is in
   view, safe-area aware. Orange primary treatment.
2. CTA weight: layered shadow stack + inset highlight on the primary .cta, hover
   lift; the existing underline-slide hover on links stays.
3. Entrance system: fade-up 24px, 500ms, cubic-bezier(0.16,1,0.3,1),
   IntersectionObserver once, 80ms group stagger. Apply to section headers, the
   step/feature cards, the proof section, the ctaband. Cap ~5 groups.
4. Hero word pull-up: split the hero H1 into word masks, translateY(110%) -> 0,
   600ms, 60ms stagger, on load. Sub and CTAs follow staggered. This is the one
   showcase item; keep everything else restrained.
5. OPTIONAL (needs founder yes on real product UI): a small marquee or static strip
   of real dashboard screenshots, labelled as the product.

## Hard floors
Plain CSS/JS only (no frameworks). prefers-reduced-motion disables everything.
Mobile-first (the site's audience arrives on phones); LCP no-regression. Preserve
byte-behaviour: PostHog snippet + events, canonical/OG, all Calendly UTM URLs, the
tagged mailto (subject "Joey%20enquiry%20(joeysdr.com)" style), sitemap/robots.

## Verification
375px + 1280px screenshots; reduced-motion pass; JS-off readability; grep preserved
items; deploy to main, curl-verify a new class live; empty-commit retrigger if Pages
flakes. KPIs: pilot-call clicks per session, pill share of calendly_click, mobile
bounce.

Commit style: plain one-liners ending
"Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>".
