---
name: wedding-invite
description: Make an interactive wedding invite website (one HTML file) from the couple's details and photos, check it on a phone-size screen, and put it live with a shareable link. Gates open on tap, scratch to reveal the date, countdown, add to calendar, function cards with dress codes, photo story, map button and RSVP on WhatsApp. Use when the user says "make my wedding invite", "wedding card website", "digital/e-invite", "shaadi invite", "interactive invite", or wants to change an invite made with this skill.
---

# Wedding invite

Turns the couple's details into a mobile-first invite website based on `template/index.html` (in the repo root). Everything the guest sees comes from the `INVITE` object at the top of that file, so most jobs are: fill the object, add photos, check, publish.

## 1 · Ask for the details (one message, skip what they already gave)
- Couple: groom and bride names, and each one's parents line (e.g. "Son of Mr. … & Mrs. …").
- Blessing line at the top (e.g. "|| Shree Ganeshaya Namah ||", a dua, or none).
- Main date and time (for the scratch card, countdown and calendar) and the city's time zone.
- Every function: name, day + time, place, dress code and two colours for it.
- Venue name, full address and a Google Maps link (on the phone: Maps → Share → Copy link).
- RSVP WhatsApp number (with country code) and the reply-by date.
- 3–6 photos for "Our Story" with a short caption each (optional; tasteful illustrations show if none).
- Closing line, e.g. "With love, the … families". Optional: a music file they have the rights to.
- Optional look change: colours (default maroon + gold) or a different style (pastel, South Indian temple gold, minimal white).

## 2 · Build
1. Copy `template/` to a new folder named after the couple, e.g. `rohan-meera/` (never edit the template itself).
2. Fill the `INVITE` object. Keep the field names; keep strings short so they fit a phone.
   - `date` is ISO with offset, e.g. `2027-02-14T19:30:00+05:30` for India.
   - `icon` per function: `haldi`, `mehendi`, `sangeet`, `baraat`, `pheras`, `reception` (anything else falls back to `pheras`).
   - Also update `<title>` and the `og:title` / `og:description` meta tags (this is the WhatsApp link preview).
3. Photos: put them in `<folder>/photos/` and reference them as `photos/1.jpg`. Shrink them first so the page loads fast on mobile data:
   - macOS: `sips -Z 1400 photos/*.jpg`
   - elsewhere: `magick mogrify -resize 1400x1400\> -quality 82 photos/*.jpg`
   If the user wants ONE file only (e.g. to send as an attachment), embed each photo as a base64 data URL instead.
4. Look changes: edit the colour variables in `:root` (and the gate colours in `.door` / `#gate`). For a different style, keep every interaction working (gate, scratch, countdown, calendar, swipe cards, story, map, RSVP) and change only CSS and artwork.

## 3 · Check (don't skip)
Open it at phone size (390 × 844) and go through it as a guest:
- Gate opens on tap; names type in; nothing overflows the arch.
- Scratching with a finger/mouse reveals the date (it auto-clears at ~45%).
- Countdown counts down to the right date; **Add to calendar** downloads a `.ics` with the right time.
- Function cards swipe and the dots follow; every dress code line fits.
- **Get directions** opens the right place; **Copy address** works.
- RSVP opens WhatsApp to the right number with the guest's name in the message.
- Long names or long venue names: check they don't wrap badly.
Fix anything off before publishing.

## 4 · Put it live (pick one; all have free plans)
- **Netlify Drop** (easiest): go to app.netlify.com/drop and drag the folder in. Sign in (free account) first so the site doesn't expire, then rename the subdomain (e.g. `rohan-meera.netlify.app`).
- **GitHub Pages**: push the folder to a repo → Settings → Pages → deploy from branch.
- **Cloudflare Pages**: Workers & Pages → Create → Upload assets.
- On claude.ai: ask Claude to show the file as an artifact, then use **Publish** to get a public link.

Tell the user: anyone with the link can see the page, so don't put phone numbers or addresses on it that they don't want guests to forward.

## 5 · Personal links for each guest
Add `?to=` to the link and the cover greets them by name:
`https://rohan-meera.netlify.app/?to=Sharma%20Family` → "Dear Sharma Family". Offer to make a list of links from a guest list (spaces become `%20`).

## Rules
- Use only photos and music the couple owns or has rights to.
- Don't invent details (dates, venues, names). Ask.
- Keep the "MADE WITH CLAUDE" footer only if the user wants it.
