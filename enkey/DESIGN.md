# ENKËY landing page: design plan

Status: **Design approved (Limestone day / Charcoal night). Next: the full build, pending a final "go".**
Prototypes are in `design/prototypes/hero-a.html` and `hero-b.html`. Screenshots are in `design/screens/`.

---

## 1. What's weak in the draft, and why it costs leads

| # | Problem in the draft | Why it hurts conversion | Fix |
|---|---|---|---|
| 1 | **The hero puts a translucent box over the photo.** The lock sits behind the text panel, and on mobile the lock disappears completely. | The product is the proof. If visitors can't see the lock in the first 5 seconds, the page reads as "another smart-lock reseller". | Put the text directly on the dark right side of the photo (A), or show the photo uncovered as an annotated panel (B). On mobile, crop so the lock is the hero. |
| 2 | **Everything is the same rounded card.** There are about 25 identical `20px`-radius boxes on one page. | There's no visual hierarchy, so nothing feels more important than anything else. It's a template tell. | Use editorial rhythm: hairlines, numbered rails, asymmetric splits. Cards only where grouping is real. |
| 3 | **The six unlock methods are a flat 6-card grid.** | That's the core differentiator, shown as a spec list. There's no "aha". | An interactive showcase: tabs on the right, a lock schematic on the left that lights up the zone for the selected method. |
| 4 | **Objections are buried.** The FAQ has 5 of the 7. Security, privacy, install mess and support are missing or are one-liners. | Paid traffic is cold. Unanswered objections mean the visitor bounces rather than asks. | A dedicated Security & Privacy section, plus 7 FAQ items mapped 1:1 to the objections. |
| 5 | **No price signal at all.** | "How much?" is the #1 silent bounce reason for a home-hardware purchase. | Price anchor: `החל מ־[X] ₪ כולל התקנה ומע״מ`, a list of what's included, and "the final price follows the fit check". |
| 6 | **No audience segmentation.** Shabbat households, landlords and adult children of elderly parents aren't spoken to. | Each is a distinct ad audience. Without a section that mirrors the ad promise, ad-to-page continuity breaks. | A "Who it's for" section with 4 segments. Each can later be anchor-linked from its own ad set (`#for-hosts` etc.). |
| 7 | **There's no persistent CTA.** Below the hero, the next step is 8 sections away. | It breaks "one obvious next step per viewport". | A sticky header CTA after the hero, a mobile bottom bar (WhatsApp / call), and a contextual CTA line at the end of each section. |
| 8 | **The WhatsApp link isn't pre-filled, and the phone `tel:` is local-format.** | It adds friction, and the lead source can't be identified in chat. | `wa.me/972527703730?text=…` pre-filled, and `tel:+972527703730`. |
| 9 | **Weak typography.** Rubik everywhere at 800 reads "app", not "architecture". | The brief asks for "quiet luxury". | A proper display/body pairing (see tokens). |
| 10 | **Inline styles everywhere, the privacy link is `#privacy`, there's no form handling, and a 290 KB+ unoptimized hero.** | Not maintainable, the legal links are broken, and the LCP is at risk. | Tokens in CSS, real `/privacy` and `/accessibility` pages, responsive AVIF/WebP hero with preload. |

**Shabbat blind spot (important, not just design):** The draft says the key works "בלי חשמל". That is true of the mechanical cylinder. However, many smart locks still **wake a sensor, beep, light up or log an event** when the handle is turned or the door opens. For an observant household, that's the actual question. The page must not claim "Shabbat-compliant". It says what's factually true (a mechanical key is included) and leaves a visible placeholder: `[לאשר מול היצרן: האם פתיחה בידית/במפתח מפעילה רכיב חשמלי כלשהו (חיישן, צפצוף, תאורה, תיעוד), והאם יש מצב שבת]`. If the lock has a certified Shabbat mode, that becomes the headline of the section and a major ad angle.

---

## 2. Message hierarchy

1. **What it is:** a smart lock with 3D face recognition, professionally installed. (eyebrow + H1 + photo)
2. **Why it's better:** no keys to lose, and 6 ways in, *including a real mechanical key*. (lead + showcase)
3. **Why trust it:** security and privacy facts, the mechanical backup, warranty and support. (security, proof)
4. **Is it for me:** families, Shabbat homes, hosts, elderly parents. (segments)
5. **What it costs and what happens next:** the price anchor, then the 3-step process, then the fit-check form.

The one action throughout is **בדקו התאמה לדלת שלכם**. WhatsApp is the low-commitment alternative. Calling is third.

---

## 3. Final section list

| # | Section | Purpose | Change vs brief |
|---|---|---|---|
| 0 | Header | Wordmark, 5 anchor links, phone. After the hero leaves the viewport it becomes sticky with a compact primary CTA. | none |
| 1 | **Hero** | The promise, the product, the primary CTA + WhatsApp, 3 micro-trust points. | none |
| 2 | **The feeling**: "לביטחון שלך מגיע שקט." | Emotional pains (key under the mat, the kid's lost key, waiting on the stairs) on the start side; video-at-the-door and entry history as two "relief" rows on the end side. Asymmetric split, not 5 cards. | none |
| 3 | **How it opens** (interactive) | 6 methods as a `role="tablist"`. Selecting one lights its zone on an SVG lock schematic and shows a one-line use case. Arrow keys / Home / End work; reduced motion = instant swap. | none |
| 4 | **Who it's for** | 4 segments, each with one concrete benefit and a deep-link anchor for ad sets. | none |
| 5 | **Shabbat** | "חכם באמצע השבוע. פשוט בשבת." A calm two-column "weekday / Shabbat" diptych: the weekday side shows every method, the Shabbat side shows only the key. Warm, restrained, no candle clip-art. | none |
| 6 | **Security & privacy** | Objections 2 and 3: where face data lives, encryption, tamper alerts, low-battery alerts and emergency power, the mechanical backup. Every spec is a placeholder. | none |
| 7 | **Process** | Fit check, then installation, then guidance and support. A numbered horizontal rail, not cards. It answers objections 1 (fit), 5 (mess) and 7 (support). | none |
| 8 | **Proof & guarantees** | 2 install-photo slots, 1 review slot, 3 guarantee cells (lock warranty, install warranty, fault response). All placeholders. | none |
| 9 | **Price anchor** | `החל מ־[X] ₪`, what's included, and the CTA. | **Placed after proof, before FAQ** (as briefed). Reason: price lands after trust is built, and the FAQ then mops up the remaining doubts right before the form. |
| 10 | **FAQ** | 7 native `<details>`, one per objection. | none |
| 11 | **Final CTA + form** | Form on one side; on the other, a large phone number, WhatsApp, and "what happens after you submit" (3 lines). | Added the "what happens next" micro-list. It's copy, not a feature, and it reduces form anxiety. |
| 12 | Footer | Wordmark, phone, privacy, accessibility, ©. | none |
| ∞ | Mobile bottom bar | `<768px` only: WhatsApp + call, shown once the hero CTA scrolls away. It hides while the form is in view so it never covers the submit button. | none |

### Proposed, not built (per "no features beyond the brief")
- **Per-segment hero variants via `?seg=shabbat|hosts|parents`**: swaps the H1 sub-line and the hero trust points to mirror the ad. It's cheap, and it's typically the single biggest lift for multi-audience paid traffic.
- **A "Shabbat mode" badge**, if the manufacturer confirms one exists (see the blind spot above).
- **A door-type photo upload in the form**: the installer qualifies the door before calling back, so fewer wasted site visits.
- **A Hebrew lead-status dashboard** on the `enquiries.status` column (or just use Supabase Studio at first).
- **A cookie/consent banner** for Pixel and GA4, if counsel deems it needed under Privacy Protection Law Amendment 13.

---

## 4. Design tokens: final theme "Limestone" (day) / "Charcoal" (night)

**Decided:** the page follows the visitor's system light/dark setting (`prefers-color-scheme`). Light = **Limestone**, dark = **Charcoal**. No manual toggle: ad visitors stay under a minute, and the system setting already covers phones on "Automatic", which switch at sunset. The brass/amber accent from the draft is retired.

### Color
Contrast is measured against the alternate section background (`--bg-2`), the stricter of the two grounds.

| Token | Limestone (light) | Charcoal (dark) | Use | Contrast light / dark |
|---|---|---|---|---|
| `--bg` | `#F1EDE6` | `#0E0F11` | page base | — |
| `--bg-2` | `#E8E3DA` | `#15171A` | alternate section | — |
| `--surface` | `#FBF9F5` | `#1A1C20` | inputs, raised panels | — |
| `--line` | `#D9D2C6` | `#272A2F` | hairlines | decorative |
| `--line-ui` | `#8A8478` | `#666B73` | input + secondary-button borders (WCAG 1.4.11) | 3.2:1 / 3.6:1 on `--bg` |
| `--text` | `#16181A` | `#F5F5F3` | headings, body | ≥15:1 |
| `--text-2` | `#3E4246` | `#C3C5C8` | secondary body | ≥9:1 |
| `--text-3` | `#5F6368` | `#999CA1` | captions, meta | 4.7:1 / 6.5:1 |
| `--accent` | `#1F4D3A` bottle green | `#8CC5A6` sage | single accent, primary CTA | 7.5:1 / 8.9:1 |
| `--accent-hi` | `#2C6A50` | `#B4DBC5` | hover, scan line | — |
| `--on-accent` | `#F6F3EC` | `#0C1A13` | text on the CTA | 8.7:1 / 9.1:1 |

One accent, green in both modes, so day and night read as the same brand. Blue was tested for night and rejected: it blends into the photo's blue light and is the category default.

### Type (2 families)

| Role | Font | Why |
|---|---|---|
| Hebrew display + Latin wordmark | **Bellefair** 400 | A thin, high-contrast Hebrew/Latin serif. Reads as gallery and architecture, not gadget. One family covers both the Hebrew headlines and `ENKËY`. |
| Hebrew body | **IBM Plex Sans Hebrew** 400/500/600 | Clean, engineered, very legible at small sizes. Its technical tone balances the elegant display face. |

Fonts are self-hosted (subset to Hebrew + Basic Latin, `woff2`, `font-display: swap`, display face preloaded) for LCP.

**Scale** (fluid, 390 to 1440):
`--fs-display: clamp(3.625rem, 3rem + 4.8vw, 8rem)` · `--fs-h2: clamp(2.25rem, 1.7rem + 2.4vw, 3.75rem)` · `--fs-h3: 1.375rem` · `--fs-lead: clamp(1.125rem, 1rem + .4vw, 1.3125rem)` · `--fs-body: 1.0625rem` · `--fs-small: .9375rem` · `--fs-micro: .8125rem`.
Line heights: display `.98`, h2 `1.05`, body `1.6`. Headlines use `text-wrap: balance`, and `&nbsp;` is placed before the last word where needed so no single word is orphaned.

### Spacing (4-based, no ad-hoc values)
`--s-1 4` · `--s-2 8` · `--s-3 12` · `--s-4 16` · `--s-5 24` · `--s-6 32` · `--s-7 48` · `--s-8 64` · `--s-9 96` · `--s-10 128`.
Section padding: `--s-9` desktop, `--s-8` mobile. Gutter: `clamp(16px, 4vw, 48px)`. Content max-width: `1360px`, prose `34em`.

### Radius
`--r-xs 2px` (labels) · `--r-sm 4px` (buttons, panels, images) · `--r-md 8px` (inputs, FAQ rows).
Near-square corners throughout. The draft used 20 to 28px pills and cards everywhere; squared edges read as architectural and match the serif.

### Elevation
None. Depth comes from the surface steps (`--bg → --bg-2 → --surface`) and hairlines, not shadows. The single exception is the soft glow on the scan line.

---

## 5. Motion plan

| Element | Motion | Duration / easing | Reduced motion |
|---|---|---|---|
| Hero face scan | A thin accent line sweeps the face mesh top to bottom, fading at the ends | 3.2 s loop, `cubic-bezier(.45,0,.25,1)`, `transform` only | static line at 70% opacity |
| Hero text | A 12px rise + fade, staggered 60 ms (eyebrow, H1, lead, CTAs). Runs once, CSS-only. | 600 ms `ease-out` | none, instantly visible |
| Section reveal | IntersectionObserver adds `.is-in`: 16px rise + fade, once | 500 ms | none, content is visible by default (no-JS safe) |
| Unlock showcase | Zone highlight cross-fades on the schematic; an accent "bolt" retracts 6px on select | 280 ms | instant swap |
| Sticky header | Slides in from the top after the hero leaves | 220 ms | appears without transition |
| Buttons | accent, then accent-hi on hover; a 2px accent focus ring with 3px offset | 150 ms | n/a |
| Light/dark | Follows the system setting; no animated switch | — | — |

Nothing animates layout properties, and there's no parallax or autoplay video. Everything is CSS, plus ~1 KB of IntersectionObserver.

---

## 6. Hero: how the direction was chosen

1. **Two layouts were prototyped** (`hero-a.html`, `hero-b.html`, brass theme). A put text over a full-bleed photo; B used a split layout with a framed photo and labelled callouts.
2. **Decision:** A's mobile-first priorities with B's labelled callouts.
3. **Theme round** (`theme-v.html`): three color/font systems on that layout. Midnight Ice (`?v=1`), **Limestone (`?v=2`, chosen)**, Graphite Signal (`?v=3`).
4. **Night mode round:** a warm-charcoal night version was replaced by Graphite Signal's neutral charcoal, keeping Limestone's fonts and a green accent.

**Final hero (Limestone):**
- Desktop: a split layout. The text is on the stone background (right, the RTL start side); a framed, cropped photo panel is on the left, with labelled callouts on the lock (3D face, code, fingerprint) and the accent scan line over the face.
- Mobile: the photo panel comes first, so the lock is visible immediately, followed by the headline and the primary CTA.
- **To fix in the build:** at 390×844 the primary CTA currently sits right at the fold. The photo panel will be shortened so the CTA is clearly above it.
- The photo is unchanged in both modes. It is a dusk scene, so it sits naturally on both stone and charcoal.

---

## 7. Placeholder list (to be filled by the business)

| Placeholder | Where |
|---|---|
| `[X]` months lock (manufacturer) warranty | hero trust point, guarantees, FAQ |
| `[X]` months installation warranty | guarantees |
| `[X]` hours fault-response time | guarantees, FAQ "who do I call" |
| `[X]` hours callback time after the form | form success state, "what happens next" |
| `החל מ־[X] ₪` starting price (incl. installation and VAT) | price section, FAQ |
| `[מה כלול במחיר]`: confirm the included items | price section |
| `[X] חודשים` battery life, battery type | security section, FAQ |
| `[מנגנון התרעה על סוללה חלשה]` | security, FAQ |
| `[פתרון חירום: יציאת USB-C / סוללה חיצונית?]` | FAQ battery |
| `[היכן נשמרים נתוני הפנים: במנעול בלבד / בענן]` | security, FAQ privacy |
| `[תקן ההצפנה]` | security |
| `[התראת פריצה / חבלה: האם קיימת?]` | security |
| `[תקן / אישור: למשל ת״י, CE]` certifications | security |
| `[סוגי דלתות נתמכים / עובי דלת]` | FAQ fit |
| `[משך התקנה משוער]`, `[האם נדרש קידוח נוסף]` | process, FAQ install |
| `[לאשר מול היצרן: האם פתיחה בידית/במפתח מפעילה רכיב חשמלי, והאם יש מצב שבת]` | Shabbat, FAQ Shabbat |
| `[אפליקציה: שם / iOS / Android]` | showcase "app" |
| `[וידאו: האם נדרש Wi-Fi / רכזת]` | feeling section |
| `[תמונת התקנה אמיתית]` ×2 | proof |
| `[ביקורת אמיתית של לקוח]`, `[שם, עיר]` | proof |
| `[לעדכון משפטי]` | /privacy, /accessibility (full text) |
| `[שם רכז/ת הנגישות, טלפון, דוא״ל]` | /accessibility |

---

## 8. Legal and commercial blind spots

- **Price display:** Israeli consumer protection rules require consumer-facing prices to include VAT. The anchor copy reads "כולל מע״מ" deliberately.
- **Privacy Protection Law, Amendment 13 (in force Aug 2025):** the lead form collects personal data, and the product itself handles biometrics. The privacy policy needs counsel, and possibly a database-registration review. The page never states where biometric data lives until the manufacturer confirms it.
- **Accessibility (תקנות שוויון זכויות, IS 5568):** the statement must name a real accessibility coordinator. That's a placeholder for now.
- **WhatsApp as a channel:** chats bypass the Supabase pipeline, so WhatsApp leads are counted only by the click event. Proposal (not built): log WhatsApp/call clicks with their UTMs to Supabase too, so every channel lands in one table.
