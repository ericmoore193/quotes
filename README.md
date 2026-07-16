# Clearview Quote Landing Page — Setup Guide

One page, one link to share. Visitors pick a coverage type and get sent to the
right quote form. Hosted free on GitHub Pages; edited with Claude Code.

## One-time setup (about 15 minutes)

### 1. Create your GitHub account
1. Go to **github.com** → Sign up, using your insurance email.
2. Pick a professional username (it appears in your page URL) — e.g.
   `ejmoore-clearview` gives you `ejmoore-clearview.github.io/...`.

### 2. Create the repository and upload these files
1. On GitHub, click **+** (top right) → **New repository**.
2. Name it `quotes` (short name = short URL). Set it to **Public**
   (GitHub Pages on a free account requires a public repo). Click **Create**.
3. On the new repo page, click **uploading an existing file**, drag in
   `index.html`, `CLAUDE.md`, and `README.md` from this folder, and click
   **Commit changes**.

### 3. Turn on GitHub Pages
1. In the repo: **Settings → Pages** (left sidebar).
2. Under "Build and deployment": Source = **Deploy from a branch**,
   Branch = **main**, folder = **/ (root)** → **Save**.
3. Wait ~1–2 minutes, refresh the page — your live URL appears at the top:
   `https://YOUR-USERNAME.github.io/quotes/`
4. That URL is the one link you share everywhere.

### 4. Connect Claude Code (desktop or web app)
1. In the Claude app, open **Claude Code** and choose to work on a
   **GitHub repository**.
2. Authorize GitHub when prompted and select your `quotes` repo.
3. That's it — Claude Code reads `CLAUDE.md` automatically, so it already
   knows what this project is and how to edit it safely.

## Your first message to Claude Code (copy-paste this)

Once the repo is connected, paste this as your first message so Claude Code
orients itself and verifies everything:

> Read CLAUDE.md first — it has the full context for this project. Then verify
> the site is ready to go live: (1) all seven quote-link hrefs in index.html
> exactly match the URLs listed in CLAUDE.md, including the Workers' Comp link
> which intentionally uses ?agent=Eric instead of ?agent_name=Eric — do not
> "fix" that; (2) the contact buttons point to tel:+15127291108 and
> mailto:ericmoore@clearviewinsurance.com; (3) the page displays my name as
> Eric "EJ" Moore in the title and footer; (4) the layout holds up at phone
> width (~375px). Report anything off before changing it.

## Everyday workflow after setup

1. Open the repo in Claude Code.
2. Ask in plain English: *"Swap the auto quote button to point at
   https://... "* or *"Add a card for boat insurance"* or
   *"Change the accent color to Clearview blue."*
3. Have Claude Code commit and push to `main`.
4. The live page updates itself within a couple of minutes. No other steps.

## Before you share the link publicly

- [ ] Replace every `REPLACE_WITH_..._QUOTE_LINK` placeholder with a real URL
- [ ] Replace `REPLACE_PHONE` and `REPLACE_EMAIL` with your real contact info
- [ ] Have your General Lines P&C license in hand — the page publicly solicits
      insurance under your name, which is licensed activity in Texas
- [ ] Run the page copy past Joe / Clearview compliance (it's public marketing
      for a licensed product — 5 minutes now beats a headache later)
- [ ] Optional: add your TX license number to the footer (not required — your
      displayed name satisfies TX ad ID rules — but it's a nice trust signal)
