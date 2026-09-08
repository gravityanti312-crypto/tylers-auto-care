# Tyler's Auto Care — what still needs Tyler's real info

This site is a rebrand of the Glass Mobile Detailing template: same layout, structure
and quote builder, restyled to a black + gold theme from Tyler's logo. Everything below
is placeholder data carried over from the template. **Do not put this live until these
are replaced.**

## 1. Contact details

| What | Placeholder in the file | Where |
|---|---|---|
| Phone (display) | `(555) 123-4567` | nav, hero, footer, sticky bar, quote success, 7 spots |
| Phone (links) | `tel:5551234567`, `sms:5551234567` | same spots |
| Email | `tylersautocare@example.com` | footer, gift-card link, form endpoints, `api/*.js` |
| City / service area | `Your City, ST` | footer contact, footer copyright, meta |
| Service-area list | Phoenix, **Your City**, Tempe, Mesa, Gilbert, Chandler, East Valley | footer |
| Instagram | `@tylersautocare` → `instagram.com/tylersautocare/` | Socials section, footer |
| Website URL in referral SMS | `https://tylersautocare.com` | referral text template |

**Real links already in** (Socials section + footer icon row):
TikTok `https://www.tiktok.com/@tylersautocare`, Facebook
`https://www.facebook.com/profile.php?id=61585491647913`. The Facebook URL was
trimmed to the bare profile id — the `mibextid` / `rdid` / `share_url` params on
the shared link are just share-tracking and are not needed. Instagram is still
the placeholder handle above; note TikTok confirms the handle `tylersautocare`,
so the Instagram URL may already be right — worth checking rather than assuming.

The email is deliberately `@example.com` so no lead form can quietly mail a stranger.
Two forms post to `formsubmit.co/ajax/<email>` — swap the address before testing them.

## 2. Reviews (important)

The `#reviews` carousel still holds **Glass Mobile Detailing's real Google reviews**,
with "Jackson" swapped to "Tyler". They are not about Tyler's business. Replace:

- every `.grev-card` (name, initials, month, text)
- `Based on **59 reviews**` — the count in two places
- the Google reviews link, currently a search URL placeholder:
  `https://www.google.com/search?q=Tyler%27s+Auto+Care+reviews`

Same goes for the hero stats: **1000+ Cars Detailed**, **5.0★ Google Rating**,
**100% Satisfaction**, and the "5-Star Google Rated" trust strip.

## 3. Online booking

The template embedded Glass's Square booking iframe. That is removed. After the
quote form submits, customers now see a **"Lock in your time"** call/text card
(`.qb-booknext` in the HTML, styles in the head). Drop Tyler's real Square /
Calendly / Housecall embed there when he has one.

## 4. Pricing

Service prices, add-on prices and the membership discounts ($60 / $40 / $80 off,
`TYLER15` / `TYLER20` / `WELCOME10` / `NEW15` / `USA` coupon codes) are all Glass's
numbers. Confirm them with Tyler.

## 5. Photos

Every photo showing the previous owner was deleted. What is in the folder now:

- `tylers-logo.jpg` / `favicon.png` — Tyler's logo
- `qbhero.jpg`, `gwagon.jpg`, `svc-full.jpg`, `svc-ext.jpg` — unbranded car shots
  (crops of the two above), used for the hero and service cards
- `pt-polish.jpg`, `pt-correction.jpg`, `pt-showcar.jpg` — stock detailing shots, no faces
- `interior.jpg` — car interior, no people
- `veh-*.png` — vehicle-size illustrations in the quote builder

Swap in Tyler's own work photos when he sends them — that is the single biggest
upgrade this site can get.

## 6. Email backend (optional)

`api/quote.js` and `api/referral.js` are Vercel serverless functions that mail the
lead through Resend. They need a `RESEND_API_KEY` env var and a verified sender
domain. Until then the forms fall back to `formsubmit.co`, so leads still arrive.
