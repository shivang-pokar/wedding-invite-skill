# The prompt (for claude.ai or the Claude app)

No Claude Code? Use this in a normal Claude chat.

1. Download [`template/index.html`](template/index.html) from this repo (open it → **Download raw file**).
2. Open a new chat at claude.ai, attach `index.html` and your photos (3–6).
3. Copy the prompt below, fill every `[ ]`, and send it.
4. When Claude shows the invite, open it on your phone-size preview and tap through it. Ask for fixes in plain words ("names are too big", "make it pastel pink").
5. Click **Publish** on the artifact to get a link, or download the file and drag it into app.netlify.com/drop.

---

```
I've attached index.html (an interactive wedding invite) and my photos.
Edit ONLY the INVITE object at the top of the file and the <title>/og meta tags
with my details below. Keep every interaction working. Embed my photos as small
base64 JPGs (max 1200 px wide) in the "story" list so it's one single file.
Show me the full updated file as an HTML artifact.

COUPLE
- Groom: [name], son of [father's name] & [mother's name]
- Bride: [name], daughter of [father's name] & [mother's name]
- Blessing line at the top: [e.g. || Shree Ganeshaya Namah || — or "none"]

MAIN DATE (for the scratch card, countdown and calendar)
- [Day, date month year] at [time], time zone [e.g. India +05:30]
- Line under the date: [e.g. Pheras at 7:30 pm]

FUNCTIONS (name | day & time | place | dress code | 2 colours)
- [Haldi | Fri 12 Feb, 10 am | Poolside Lawn | Shades of yellow | yellow, light yellow]
- [Mehendi | … | … | … | …]
- [Sangeet | … | … | … | …]
- [Baraat | … | … | … | …]
- [Pheras | … | … | … | …]
- [Reception | … | … | … | …]

OUR STORY (one caption per photo, in the order attached)
- Photo 1: [caption]
- Photo 2: [caption]
- Photo 3: [caption]

VENUE
- Name: [venue name]
- Address: [full address]
- Google Maps link: [paste link]

RSVP
- WhatsApp number with country code, no +: [e.g. 9198XXXXXXXX]
- Reply by: [date]

CLOSING LINE: [e.g. With love, the Mehta & Rathore families]
COLOURS/STYLE (optional): [keep maroon & gold / pastel pink / South Indian gold / …]
```

**Tip:** send each guest a personal link by adding `?to=Their%20Name` to the end. The cover then says "Dear Their Name".

**Making one from scratch instead (no template):** ask Claude for "a single-file, mobile-first, interactive wedding invite website (HTML artifact)" and list the same details plus the interactions you want: doors that open on tap, scratch to reveal the date, countdown, add to calendar, swipeable function cards with dress codes, photo carousel, Google Maps button, WhatsApp RSVP. The template is faster and already tested.
