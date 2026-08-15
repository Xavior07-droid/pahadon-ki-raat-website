# Pahadon Ki Raat — पहाड़ों की रात

A full-screen, glassmorphic music site built from your screenshot, with real YouTube
playback and an owner-only stats dashboard.

## Files
- `index.html` — the site itself
- `stats.html` — password-gated owner dashboard (linked quietly from the ⋮ settings menu → "Site info")
- `assets/bg.jpg` — your background image

## Deploy it (any of these work, all free)
1. **Netlify / Vercel (drag & drop)** — zip this folder, drag it onto app.netlify.com/drop, done.
2. **GitHub Pages** — push this folder to a repo, enable Pages on the `main` branch.
3. **Cloudflare Pages** — same idea, drag-and-drop deploy.

No build step, no server, no dependencies to install — it's plain HTML/CSS/JS.

## Before you go live
- **Change the owner password.** Open `stats.html`, find `OWNER_PASSWORD = ""` near
  the top of the `<script>`, and set your own. Since this is a static site with no backend, this is a
  *deterrent*, not real security — anyone who views page source could find it. If you ever want this
  properly locked down, that needs a small backend or a host-level password wall (Netlify/Cloudflare
  both offer this for free).
- **Support Me link** — currently points to `https://www.buymeacoffee.com/yashkatekhq`; swap in your real link
  (UPI, Buy Me a Coffee, Patreon, whatever you use).
- **Background image** — I used your screenshot directly at its original resolution (746×421). It looks
  fine blurred/darkened as a backdrop, but if you have the original higher-res artwork, drop it in as
  `assets/bg.jpg` for a sharper look on large screens.

## What's real vs. simulated
- **Music playback is real** — 7 verified YouTube tracks (Safarnama, Kabira, Ilahi, Nadaan Parinde,
  Iktara, Zara Sa, Roobaroo) play through the actual YouTube player, just visually hidden so only your
  custom glass player shows. Add more by extending the `PLAYLIST` array at the top of the script in
  `index.html` — just paste in more real YouTube video IDs.
- **"628 listening"** — kept as a decorative, gently-drifting number like in your mockup, not a real
  server headcount (a real one needs a backend with live connections, which a static site can't do).
- **Stats dashboard** — total visits and per-song play counts are genuinely global (tracked via a free
  keyless counter API, shared across every visitor). Session details (device, referrer, screen size) are
  local to whichever browser is viewing the dashboard, since a static site has no way to see other
  people's devices. The dashboard explains this distinction on-page too.

## Customizing
- Swap "Yash" in the footer/credits by searching for `Yash` in `index.html`.
- Mood themes (Bonfire / Moonlight / Deep Night / Misty Dawn) are CSS filter presets on the same image —
  add real alternate images per mood later if you want a bigger visual shift.
