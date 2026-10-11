# ENKËY landing page: design plan

Status: **Step 1. Waiting for a hero direction choice before the full build.**
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

## 4. Design tokens

Both prototypes share these tokens. Only the type families differ.

### Color
| Token | Value | Use | Contrast on `--ink-950` |
|---|---|---|---|
| `--ink-950` | `#0A0C0E` | page base | — |
| `--ink-900` | `#0F1215` | alternate section | — |
| `--ink-850` | `#14181C` | surface / inputs | — |
| `--ink-800` | `#1B2025` | raised surface | — |
| `--line` | `#252B31` | hairlines | decorative |
| `--line-strong` | `#353D46` | decorative dividers on surfaces | decorative |
| `--line-ui` | `#636C76` | input + ghost-button borders (WCAG 1.4.11) | ≥3:1 on ink-950 and ink-850 |
| `--text` | `#F3EFE7` | headings, body | 17.1:1 |
| `--text-2` | `#C5C9CD` | secondary body | 11.8:1 |
| `--text-3` | `#959CA4` | captions, meta | 7.1:1 |
| `--brass` | `#E6AE4E` | single accent, primary CTA | 9.8:1 |
| `--brass-hi` | `#F3CC85` | hover, placeholder brackets | 12.9:1 |
| `--on-brass` | `#120E06` | text on brass | 9.6:1 on brass |
| `--shabbat-950` | `#14110B` | warm ground for the Shabbat section only | — |

There's one accent. The blue in the photograph is never sampled into UI, so the brand stays brass.

### Type (≤3 families)

| Role | Direction A | Direction B |
|---|---|---|
| Hebrew display | **Frank Ruhl Libre** 800/900. A Hebrew serif with real stroke contrast; reads "architecture/editorial". | **Rubik** 900, tight tracking. Bold and geometric; reads "engineered hardware". |
| Hebrew body | **Heebo** 400/500/600 | **Rubik** 400/500 |
| Latin wordmark + numerals | **Syne** 700/800 | **Syne** 700/800 |

Fonts are self-hosted (subset to Hebrew + Basic Latin, `woff2`, `font-display: swap`, display face preloaded) for LCP.

**Scale** (fluid, 390 to 1440):
`--fs-display: clamp(3.5rem, 3rem + 4.6vw, 7.75rem)` · `--fs-h2: clamp(2.25rem, 1.7rem + 2.4vw, 3.75rem)` · `--fs-h3: 1.375rem` · `--fs-lead: clamp(1.125rem, 1rem + .4vw, 1.3125rem)` · `--fs-body: 1.0625rem` · `--fs-small: .9375rem` · `--fs-micro: .8125rem`.
Line heights: display `.92`, h2 `1.08`, body `1.6`. Headlines use `text-wrap: balance`, and `&nbsp;` is placed before the last word where needed so no single word is orphaned.

### Spacing (4-based, no ad-hoc values)
`--s-1 4` · `--s-2 8` · `--s-3 12` · `--s-4 16` · `--s-5 24` · `--s-6 32` · `--s-7 48` · `--s-8 64` · `--s-9 96` · `--s-10 128`.
Section padding: `--s-9` desktop, `--s-8` mobile. Gutter: `clamp(16px, 4vw, 48px)`. Content max-width: `1360px`, prose `34em`.

### Radius
`--r-xs 4px` (tags, ticks) · `--r-sm 8px` (panels, images) · `--r-md 14px` (inputs, FAQ rows) · `--r-pill 999px` (buttons only).
The draft used 20 to 28px everywhere. Tighter radii read as architectural; pills are reserved for actions, so actions are instantly recognizable.

### Elevation
None. Depth comes from surface steps (`ink-950 → 900 → 850`) and hairlines, not shadows. The single exception is the brass glow on the scan line.

---

## 5. Motion plan

| Element | Motion | Duration / easing | Reduced motion |
|---|---|---|---|
| Hero face scan | A brass line sweeps the face mesh top to bottom, fading at the ends | 3.2 s loop, `cubic-bezier(.45,0,.25,1)`, `transform` only | static line at 70% opacity |
| Hero text | A 12px rise + fade, staggered 60 ms (eyebrow, H1, lead, CTAs). Runs once, CSS-only. | 600 ms `ease-out` | none, instantly visible |
| Section reveal | IntersectionObserver adds `.is-in`: 16px rise + fade, once | 500 ms | none, content is visible by default (no-JS safe) |
| Unlock showcase | Zone highlight cross-fades on the schematic; a brass "bolt" retracts 6px on select | 280 ms | instant swap |
| Sticky header | Slides in from the top after the hero leaves | 220 ms | appears without transition |
| Buttons | brass, then brass-hi on hover; a 2px brass focus ring with 3px offset | 150 ms | n/a |

Nothing animates layout properties, and there's no parallax or autoplay video. Everything is CSS, plus ~1 KB of IntersectionObserver.

---

## 6. The two hero directions

### A: "Nightfall Editorial" (Frank Ruhl Libre + Heebo)
- The full-bleed photo is the stage. Text sits directly on the photo's dark right half (the RTL start side). No box, just a gradient that deepens the existing darkness.
- A large serif H1, with "יש אותך." in brass.
- A brass scan line sweeps the face mesh, which ties the brand color into the product moment.
- Mobile: a 380px crop centered on the lock and face, so the lock is ~300px tall. The headline overlaps the fade, and the primary CTA sits above the fold at 390×844.
- **Strength:** the most emotional and premium, with the strongest "quiet luxury" read. The product is huge on mobile.
- **Risk:** the serif is less "tech". It needs the showcase section to carry the "engineered" message.

### B: "Anatomy" (Rubik 900 + Syne)
- An asymmetric split: a massive Rubik headline on the right; on the left, a framed, cropped photo with brass corner ticks and **annotated callouts** (3D face, code, fingerprint).
- The photo becomes a spec drawing, so the "six ways in" story starts in the hero.
- **Strength:** explains the product at a glance and feels engineered.
- **Risk:** on mobile the product image falls below the fold, because the CTA has to come first. The callouts are small at 390px.

**My recommendation: A**, borrowing B's annotation language for section 3 (the showcase schematic). A wins the 5-second test on mobile, where most paid social traffic lands: the visitor sees the lock, the face scan, the promise and the CTA on one screen.

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
