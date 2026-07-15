# Cal & Carb Counter

One-screen keto app: search or scan a food, see net carbs, tap to add to today's total, watch the daily ring fill. Live web version: https://lionel-cmyk.github.io/keto-ring/

The entire app is a single self-contained file, `index.html` (no build step, no dependencies). Data sources: a built-in table of ~90 whole foods, plus the Open Food Facts public API for packaged products and barcode lookup (net carbs = carbohydrates − fiber). The day log and goal persist in `localStorage` and reset each morning.

## Getting this into TestFlight

TestFlight needs a native iOS binary, so the web app must be wrapped. Capacitor is the fastest path (~1 hour):

```bash
npm init -y
npm install @capacitor/core @capacitor/cli @capacitor/ios
mkdir www && cp index.html apple-touch-icon.png www/
npx cap init "Cal & Carb Counter" com.calcarb.app --web-dir=www
npx cap add ios
npx cap open ios
```

Then in Xcode:
1. Set the signing team (needs an Apple Developer account, $99/year).
2. Product → Archive → Distribute App → TestFlight.

### Requirements
- macOS with Xcode 15+
- Apple Developer Program membership (the account that will own the App Store listing later — worth deciding whose account before uploading)

### Worthwhile native upgrades (in priority order)
1. **Camera barcode scanning** — the web version asks the user to type the barcode digits. Add `@capacitor-mlkit/barcode-scanning` (free, on-device) and call it from the existing scan button; the lookup code (Open Food Facts `/api/v2/product/{code}.json`) already works.
2. **Haptic tick** when the ring updates (`@capacitor/haptics`).
3. Keep everything else as is — the product's entire positioning is "one screen, nothing else."

### App Review notes
- Don't add health/medical claims to the App Store listing (keywords like "diabetes" will trigger extra review).
- Open Food Facts data is ODbL-licensed — add a "Data from Open Food Facts" line in the listing description or an about link.
