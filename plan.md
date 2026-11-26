# Wedding Invitation Website: Plan

Piu Pramanik & Soumen Pal. Marriage Ceremony on 26 Jan 2027 and Reception on 27 Jan 2027.

## 1. Goal

A modern, minimalist, mobile-first invitation website that is easy to deploy (no build step, no server) and easy for guests to use: directions, calendar, travel help, gifts, card downloads, and their own language.

## 2. What was built

| Area | Details |
|---|---|
| Design | Navy, ivory and gold palette that echoes the printed card. Peacock-feather and gold touches. One fade-in when the page opens. |
| Hero | Couple photo in an arch frame, blessing line, names, invitation line, first event date. |
| Countdown | Live days, hours, minutes and seconds to the Marriage Ceremony. |
| Events | Two cards (Marriage Ceremony, Reception) with date, weekday, time, venue and three buttons: **Get directions** (Google Maps), **Google Calendar**, **Apple / Outlook** (.ics). A button saves both events at once. |
| Travel | Collapsed "Travelling by train?" section listing trains to Garhbeta (GBA). |
| RSVP | Opens WhatsApp when a number is set, otherwise shares the invitation. |
| Blessing zone | Collapsed section with gift-card email and UPI (copy buttons and a UPI app link). |
| Invitation cards | Collapsed section with a bride's-side and a groom's-side card. Each has **Download card** (JPG) and **Download PDF**. Also a QR code of the site link (downloadable). |
| Languages | English, Hindi, Bengali, Odia, Telugu. Menu at top right, choice remembered, and `?lang=bn` style links. |
| Music | ♪ button at bottom left. Built-in soft melody, or your own mp3. Starts on the guest's first tap (`autoMusic`). |
| Share | Share button (phone share sheet or copy link). |

## 3. Files (all must be deployed together)

```
wedding-site/
├── index.html        the whole site (HTML, CSS, JS, translations)
├── couple.jpg        hero photo
├── card-bride.jpg    bride's-side card image
├── card-groom.jpg    groom's-side card image
├── card-bride.pdf    bride's-side printed invitation (4 pages)
├── card-groom.pdf    groom's-side printed invitation (4 pages)
└── song.mp3          optional, your own music
```

Keep this plan file outside the deploy folder so it is not published.

## 4. Settings you can change (the `CONFIG` block at the top of the script in `index.html`)

- `bride`, `groom`
- `events`: title, `date`, `start`, `end`, `venue`, `mapUrl` (one entry per event)
- `whatsapp`: number for RSVP, country code first, no `+`
- `giftEmail`, `upiId`, `upiName`
- `music`: empty for the built-in melody, or `"song.mp3"`
- `autoMusic`: `true` or `false`
- `cards`: image and PDF file names
- `trains`: train list
- `siteUrl`: the final site link (used by the QR code and Share)
- Hide switches: `showTrains`, `showBlessings`, `showCards` (set to `false` to remove a section)

## 5. Deployment

**Netlify Drop (about 1 minute)**
1. Put all files in one folder.
2. Go to app.netlify.com/drop and drag the folder in.
3. Rename the site under **Site settings → Change site name**.
4. To update later, drag the folder onto the site's **Deploys** tab.

**GitHub Pages (alternative)**
1. Create a public repo and upload all files.
2. **Settings → Pages → Deploy from a branch → main → / (root)**.

**After deploying**
1. Paste the final link into `siteUrl`, re-upload `index.html`.
2. Download the QR code again from the site (it now points to the final link).
3. Optional: connect your own domain in Netlify under **Domain management**.

## 6. Open items

| # | Item | Why it matters |
|---|---|---|
| 1 | Venue text | The site says "Garhbeta, West Medinipur" for both events. Printed cards name the villages (ceremony at the bride's home, Chhoto Rangta, Mangalpur; reception at the groom's home, Sutaharar, Hamgarh). Decide which to show. |
| 2 | Reception year on the Sutaharar card image | The image says 2026. The printed card and the site say 2027. Fix and regenerate the image. |
| 3 | Event times | 8:00 PM and 6:00 PM were given by the family. Printed cards show no time. Confirm. |
| 4 | Map links | Ceremony uses the bride's link and reception uses the groom's link. Confirm both open the right place. |
| 5 | WhatsApp number | Not set yet, so RSVP only shares the page. |
| 6 | Translations | Written by Claude. A native speaker should read Hindi, Bengali, Odia and Telugu, and the spellings of the names in each script. |
| 7 | Aranyak Express days | Read as Mon to Sat from a screenshot. Confirm on IRCTC or NTES. |
| 8 | Train list | The screenshot was cut off, so there may be more trains. |
| 9 | Music | Replace the built-in melody with a licensed or personal mp3 if wanted. |
| 10 | WhatsApp link preview | The preview image path is relative. After deploying, change `og:image` in `index.html` to the full web address of `couple.jpg`. |

## 7. Pre-launch test checklist (on a real phone)

- [ ] Page opens, photo shows, no sideways scrolling
- [ ] Countdown runs
- [ ] Each language in the menu switches all text
- [ ] **Get directions** opens the correct place for each event
- [ ] Google Calendar and .ics downloads show the right date, time and venue
- [ ] Train, Blessing zone and Invitation cards sections open and close
- [ ] Copy email, Copy UPI ID and **Pay with UPI app** work
- [ ] Download card (JPG) and Download PDF work for both sides
- [ ] QR code appears and scans to the live site
- [ ] ♪ starts and stops music, and music starts on the first tap
- [ ] Share button works, and the link preview in WhatsApp shows the photo
- [ ] Open the link on both Android and iPhone

## 8. Possible next steps

- A proper RSVP form (name, number of guests, message) saved to Google Sheets or sent to WhatsApp
- Guest name in the link, for example `?to=Sharma Family`
- Day-of-wedding schedule or timeline
- Photo gallery or "our story"
- Tap-to-call buttons for family contacts
- Road directions and parking or stay options near the venues
