# Wedding invite with Claude

An interactive wedding invite website, made with Claude, that guests open from a link on WhatsApp.

- **Gates open** on tap (with a personal "Dear Sharma Family" greeting)
- **Scratch the gold** to reveal the date
- Live **countdown** + **Add to calendar** (iPhone, Android, desktop)
- **Swipe** through every function with its **dress code** and colours
- **Our Story** photo carousel
- **Get directions** straight to Google Maps, copy address
- **RSVP on WhatsApp** in one tap

One HTML file. No app, no backend. Hosting can be free (Netlify, GitHub Pages, Cloudflare Pages).

**Live demo:** open [`template/index.html`](template/index.html) in your browser (download it first) and switch to phone view.

## Make yours

### Option A · Claude chat (claude.ai or the Claude app)
Follow [PROMPT.md](PROMPT.md): attach the template + your photos, paste the prompt with your details, publish.

### Option B · Claude Code (the skill)
```bash
git clone https://github.com/shivang-pokar/wedding-invite-skill
cd wedding-invite-skill
claude
```
Then say: **"Make my wedding invite"**. Claude uses `.claude/skills/wedding-invite/`, asks for your details, builds a copy in its own folder, checks it at phone size, and helps you put it live.

To use the skill in another project, copy `.claude/skills/wedding-invite/` and `template/` into it.

## What it costs
- This repo, the template and the prompt: free (MIT).
- Claude: you need a Claude account. Big files with many photos can hit free-plan limits; a paid plan avoids that.
- Hosting: the free plans of Netlify / GitHub Pages / Cloudflare Pages are enough. A custom domain (e.g. `rohanwedsmeera.com`) costs extra.

## Good to know
- Anyone with the link can open the page. Don't add details you don't want forwarded.
- Use your own photos and music you have the rights to.
- Change the look by asking Claude ("make it pastel", "South Indian temple gold"); every interaction stays.

## Licence
MIT. Made by @techonomics.in.
