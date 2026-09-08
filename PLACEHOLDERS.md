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

## 2. Reviews — DONE

The `#reviews` carousel now holds **Tyler's 45 real Google reviews** (owner replies
deliberately not shown), and every "read our reviews" button across the site points at
`https://share.google/WyiCVYDfeW9cFIlP5`.

Two things to sanity-check:

- **The count says "Based on 46 reviews."** That is 45 reviews with text plus one
  rating-only entry, counted from the list that was pasted in. If the Google profile
  shows a different total, change it in two places (`.reviews-count` and `.qb-hr-count`).
- **Four reviews were truncated by Google's "… More"** — Terese Fairfield, Ray Morris,
  Anna Otto, Natasha Caudle. Those are cut at the last complete sentence rather than
  guessed at. Paste the full text in if you want them whole.

Still unverified, and carried over from the template: the hero stats
**1000+ Cars Detailed** and **100% Satisfaction**, and the "Same-Day Booking Available"
trust-strip claim. The 5.0★ rating is consistent with the reviews.

**Service area — worth asking Tyler.** Several of his own Google replies mention
**Bloomington** ("here in Bloomington", "your car detailing in Bloomington"). The footer
still says `Your City, ST` and lists Phoenix / Tempe / Mesa / Gilbert / Chandler / East
Valley, which are the template's Arizona cities. Confirm the city and state (Bloomington
IN vs IL) before swapping those in — I did not want to guess the state.

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
