# Sip & Claude · Dallas — Identity Maker

A community memento tool for Sip & Claude attendees. Pick a hat, a skin tone, your drink (Claudetini, The Opus, The Sonnet, The Haiku, plus more), and your vibe. Get a shareable card **and** a transparent pixel of your character — to post that you were there, or to use as a Discord/Slack/LinkedIn avatar.

**Built by Tolani Omitokun, host of Sip & Claude Dallas.**

Forked from the [Built with Opus 4.7 Identity Maker](https://opus47identitymaker.vercel.app) — same pixel language, different event branding.

---

## Why this exists

Sip & Claude is a casual community meetup in Dallas — laptops, cocktails, and Claude. After each event, attendees should walk away with something they're proud to post. This tool produces a shareable card with the Sip & Claude pixel character + a transparent pixel for avatars.

Every pixel is generated client-side in the browser using SVG and Canvas. No image-gen model. No photo upload. Your face stays your face — your *vibe* is the avatar.

## What it does

- **Agent persona** (free text) — Cowgirl Agent, Night Owl Agent, Coffee Pirate Agent, whatever you invent
- **Name + tagline** (free text)
- **Event role** — Host (gold) / VIP (crimson) / Attendee (ember). Sets the card accent.
- **Skin tone** — 5 options
- **Headwear** — Cowboy hat / Beanie / Headphones / Cap / None
- **What's in your hand** — 14 options including all Sip & Claude signature drinks (Claudetini, The Opus, The Sonnet, The Haiku, Claudeccino, Claudeade, Matcha, Water) plus tools and vibes
- **Facial features** — None / Lashes / Glasses (black, green, orange)
- **Two downloads**:
  - **Card** — 1080 × 1080 PNG, ready for LinkedIn, X, Instagram, Discord posts
  - **Pixel only** — transparent PNG of just the character, for Discord/Slack/site avatars

## Deploy

Already deployed on Vercel. To redeploy after edits:

```bash
cd sipandclaude_identity_maker
vercel --prod
```

To deploy to GitHub Pages instead, push to a public repo and enable Pages in Settings.

## Design system

- Paper `#F5F0E6` · Ink `#1A1612` · Ink-soft `#4A403A`
- Gold `#C9A24C` (Host) · Crimson `#A62626` (VIP) · Ember `#D97740` (Attendee)
- Instrument Serif (display) · Fraunces (body) · JetBrains Mono (monospace accents)
- Subtle SVG noise grain for paper texture

## Tech notes

- One HTML file, no build step
- All rendering in SVG, inserted via DOMParser + replaceChildren (no innerHTML)
- All user text escaped before being placed in SVG `<text>` elements
- PNG export via canvas: serialize SVG → image → drawImage → `canvas.toBlob`

## License

MIT. Remix for your own community events.
