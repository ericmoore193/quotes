# Clearview Quote Landing Page

## What this project is

A single-page public landing site for EJ Moore, Customer Sales Representative at
**Clearview Insurance Agency LLC** (independent agency, 40 states, Texas hub in
Cedar Park; HQ Uniondale NY). The page is a hub of "get a quote" buttons — each
button sends a visitor to one of EJ's existing quote inquiry links (carrier or
agency quote forms). The goal: EJ shares ONE link (this page) anywhere — texts,
QR codes, referral partners, social — and visitors self-select the coverage type
they want.

## Architecture — keep it simple

- **One file**: everything lives in `index.html` (HTML + CSS inline, no build
  step, no framework, no dependencies). Keep it that way unless EJ asks otherwise.
- **Hosting**: GitHub Pages, deployed straight from the `main` branch root.
  Any commit to `main` auto-publishes within a minute or two.
- No forms are processed on this page itself — all buttons are outbound links.

## Current state

All seven quote links are live (cv-insurance.co forms, tagged with
`?agent_name=Eric` — except Workers' Comp, which the agency link uses
`?agent=Eric` for; do not "fix" that param without EJ confirming). Cards are
grouped into Personal Coverage (Personal Auto, Homeowners, Life) and Business
Coverage (Commercial Auto, Commercial Insurance, General Liability, Workers'
Comp). Contact info is real: (512) 729-1108 / ericmoore@clearviewinsurance.com.
Display name on the page is Eric “EJ” Moore (he goes by both — keep that
format in the title, meta description, and footer). Form submissions land in
EJ's agent CRM.

## Page anatomy (top to bottom)

Sticky utility bar (wordmark + phone) → flat navy masthead with EJ's
"business card" panel overlapping into the next band → "What happens after
you click" steps → Personal coverage (3 cards) → Business coverage (2×2) →
"A note from EJ" → navy contact band → footer. Cards collapse to tappable
list rows under 720px. A ~15-line inline script adds a scroll-reveal
animation (JS-gated: with JS off or reduced motion on, everything is simply
visible). No emoji anywhere — icons are hand-drawn inline SVGs (24×24,
1.75 stroke, navy) with exactly one small gold detail each.

## How to make the common edits

- **Swap a quote link**: edit the `href` on the relevant card's
  `<a class="cta">`. Keep `target="_blank" rel="noopener"` and preserve the
  `agent_name=Eric` tag so submissions credit EJ.
- **Add a coverage type**: copy an entire `<div class="card">...</div>` block
  inside the appropriate section's grid, edit the SVG icon/title/description/
  href, and give it the next `--i` value for the reveal stagger.
- **Colors/branding**: CSS variables at the top of the `<style>` block
  (`--navy`, `--accent`, etc.). Current values are the Clearview brand colors
  sampled from clearviewinsurance.com and its logo (navy `#073252`, blue
  `#0174aa`, gold `#fcc440` — gold is for small accents only). If the agency
  ever supplies an official style guide or logo file, reconcile against it
  there / in the header.
- **License number**: optional. Texas ad rules (28 TAC Subchapter B) require
  identifying the responsible party by full licensed name, registered assumed
  name, OR license number — the name in the footer already satisfies this.
  Adding the number to `#license-line` once issued is still worthwhile (TDI
  lookup verifiability, carrier co-marketing guidelines often want it).
  The real compliance gate for going live: EJ's General Lines P&C license in
  hand + Joe/compliance sign-off, since the page publicly solicits insurance.

## Constraints and cautions

- EJ is a licensed-track CSR, not yet a producer. Before adding language that
  promises rates, binds coverage, or names specific carriers publicly, EJ should
  clear it with Joe Kampert / Clearview compliance. Keep copy to "request a
  quote" framing.
- Don't add analytics, trackers, or third-party scripts without EJ asking.
- Don't collect any personal data on this page itself (no forms here) — that
  keeps the page free of privacy/compliance obligations. If EJ wants on-page
  intake forms later, discuss options (Netlify Forms, Formspree, Google Forms
  embed) and the data-handling tradeoffs first.

## Possible future work (only when EJ asks)

- QR code pointing at the page (for move-in packets, business cards)
- Custom domain instead of `*.github.io`
- Per-partner co-branded versions (e.g., a realtor's version of the page)
- Simple click tracking to see which coverage types get the most interest
