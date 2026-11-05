# under-pressure

JJ's Pressure Test Analyzer. Enter 1-minute pressure readings, see the loss trend, and get a PASS / FAIL against the pressure-test criteria (minimum test pressure with a maximum, loss rate over the last 5 minutes, total loss, loss trend). It finds the best N-minute stretch that meets the criteria.

## Links (these never change)
- **Phone:** https://almightyjoe.github.io/under-pressure/
- **Desktop:** https://almightyjoe.github.io/under-pressure/desktop/

Both addresses always serve the newest revision. The revision number is shown inside the page (top of the screen), not in the address, so old links and bookmarks keep working.

## Your data stays on your device
Everything is calculated in your own browser. Readings are never sent anywhere, and nothing is shared between people. If several people use the page at the same time, each one only sees their own readings. Readings are saved in that browser on that device, so a different phone or browser starts empty.

## Phone version
`index.html` at the top level (MOBILE REV 1.2). Open the link on an iPhone or Android and use "Add to Home Screen". It works offline after the first visit.

## Desktop version
`desktop/index.html` (currently REV 1.9). Adds loading a test log (CSV), a chart with hover and drag-to-select, and unlimited readings. To keep a copy on your computer, open the link and use the **Download app** button, or use the file in this repo.

## Earlier versions
Every desktop revision is kept in `desktop/archive/` (REV 1.6 is the formal release and the fallback). See `CHANGELOG.md` for the history.

This is a calculation aid. Confirm results against your official test criteria.
