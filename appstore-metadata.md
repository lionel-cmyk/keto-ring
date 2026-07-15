# Cal & Carb Counter — App Store metadata pack

Everything needed to fill in App Store Connect.
Assets: `appstore-icon-1024.png` (1024×1024, solid background) · `appstore-screenshots/` (3 × 1290×2796, iPhone 6.7" — the required size; App Store Connect auto-scales them for smaller devices).

## Identity & ownership
- **App name:** Cal & Carb Counter
- **Subtitle (30 chars):** Keto net carbs, made simple
- **Bundle ID:** com.etwintech.calcarb
- **Owner / seller:** Etwintec (Jo's organization developer account uploads and owns the app)
- **Copyright:** © 2026 Etwintec
- **Support URL:** https://github.com/lionel-cmyk/keto-ring
- **Category:** Health & Fitness (secondary: Food & Drink)
- **Price:** Free (monetization decided after TestFlight validation)

## Keywords (100 chars)
`net carbs,carb counter,keto tracker,low carb,carb tracking,ketosis,keto diet,macro,carbs`

## Promotional text (170 chars)
One screen. Search a food, see net carbs, tap to add. A daily ring shows exactly where you stand. No accounts, no ads, no clutter.

## Description
Cal & Carb Counter does one thing perfectly: it counts your net carbs and calories.

Search any food — or look up a barcode — see its net carbs instantly, and tap to add it to your day. A single ring fills as you eat: green when you're safe, amber when you're close, red when you're over. That's the whole app.

• Instant search across common whole foods, plus millions of packaged products
• Net carbs done right: total carbohydrates minus fiber
• Calories tracked alongside, without getting in the way
• Daily goal presets: 20g strict, 30g moderate, 50g liberal, 100g low-carb
• Your log lives on your device. No account. No email. Nothing to set up.

No meal plans, no recipes, no social feed, no premium popups. If you want a hundred features, there are other apps for that. If you want to know one number — how many carbs you have left today — this is the one.

Packaged-food data from Open Food Facts.

## App Review / privacy answers
- **Privacy nutrition label:** Data Not Collected (everything stays in local storage; the only network calls are anonymous food lookups to Open Food Facts)
- **Privacy policy URL:** https://lionel-cmyk.github.io/keto-ring/privacy.html
- **Health claims:** none made in-app; avoid "diabetes"/medical wording in the listing
- **Age rating:** 4+
- **Data attribution:** Open Food Facts (ODbL) — credited in description

## TestFlight "What to Test" note
Log everything you eat for a few days. We're testing: (1) is search fast enough at the fridge door, (2) is the built-in food list missing anything you eat weekly, (3) do you trust the ring at a glance. Barcode entry is manual in this build — camera scanning comes in the next build.

## Publish checklist (Jo)
**Phase 1 — TestFlight (can be done today)**
1. Clone the repo, follow README (Capacitor wrap, ~1 hour)
2. In App Store Connect: create the app record (name, bundle ID, primary language English U.S.)
3. Upload build via Xcode → Archive → Distribute
4. TestFlight → add internal testers (Lionel's Apple ID email) — no review needed, invite lands in minutes

**Phase 2 — App Store release (after test week + camera scanning)**
1. Add camera barcode scanning (see README — @capacitor-mlkit/barcode-scanning)
2. Fill listing from this file: subtitle, promo text, description, keywords, category
3. Upload the 3 screenshots from `appstore-screenshots/`
4. App Privacy: select "Data Not Collected" (truthful — see privacy section)
5. Privacy policy URL: https://lionel-cmyk.github.io/keto-ring/privacy.html
6. Age rating questionnaire: everything "None" → 4+
7. Submit for review (first review typically 24–48h)
