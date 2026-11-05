# JJ's Pressure Test Analyzer — changelog

## REV 1.7 (desktop)
- Minimum test pressure quick buttons: **4,500 / 5,000 / 7,500 / 8,000 / 10,000** (or type any number). The band (for example 8,000–8,400) is shown next to it.
- **Maximum test pressure** can be set exactly in Settings (blank = minimum + 5%).
- REV 1.6 stays unchanged as the fallback.

## MOBILE REV 1.1
- Same pressure buttons and an optional exact maximum test pressure on the phone version.

## MOBILE REV 1.0 (separate phone / GitHub Pages app, in `docs/`)
- Phone-first page for iPhone and Android: pick the test criteria, type 1-minute readings, see the loss trend and PASS / FAIL.
- Same calculation engine as desktop REV 1.6 (checked on 500 random tests with identical results): pressure band, last-5-minute loss rate, total-loss cap, non-worsening loss trend, best N-minute period.
- Shows KEEP GOING / BUILDING / TOO HIGH while the test is still in progress instead of calling it a fail, sticky result bar, tap a reading to fix it, skip / undo, share or copy the result, works offline once opened (installable to the home screen).
- Left out on purpose: file import, chart range selection, sections table.
- Desktop REV 1.6 is unchanged and stays the fallback.

## REV 1.6 — FORMAL PUBLIC RELEASE (current)
Designated the latest and greatest version and the formal public release. File: `JJs-Pressure-Test-Analyzer-REV1.6.html`. Git tag: `REV-1.6`. Changes after this point are made as a new revision; this file is left as is.

- **Chart hover**: the time (clock and elapsed) and pressure of the reading under the mouse, with a marker and a readout line under the chart.
- **Live selection calculation**: while you drag across the chart, the duration, start/end/lowest/highest pressure, total loss, loss rates and every pass/fail check are calculated on the fly below the chart. Releasing the mouse makes it the judged period. With nothing being dragged the panel shows the currently judged period.

## REV 1.5
- **Pass/fail now follows the pressure-test rules**: the pressure must stay between the minimum test pressure (5,000 / 7,500 / 10,000 or custom) and 5% above it for the whole period; the loss rate must be under the limit over the **last 5 minutes**; total loss within the cap for the test length (75 psi / 15 min); loss trend not worsening. A note says whether the pressure was bled back to 0 afterwards.
- **Best N-minute period** (new default): every N-minute period in the data is checked and the one that meets the criteria best is judged, so a log with the build-up and bleed-off in it still gets a fair result. Shows how many periods passed. Latest and Custom range are still available; clock times are shown when the data came from a file.
- Chart shows the minimum / maximum test pressure lines.
- Fixed: after **New test**, loading a file no longer shows a stale "different file or gauge" warning.
- Removed the optional "every section must pass" setting (the rules above replace it).

## REV 1.4
- **＋ New test** button (top right): clears the readings, test name and chosen range, keeps your settings, asks first, and can be undone with **↶ Undo**. Replaces the old Clear button.

## REV 1.3
- **Load data from a test log**: drag a file onto the page, **Open file**, or **Paste data** (Ctrl+V anywhere). Works with .csv, .txt, any extension, or none; the contents decide. Comma or tab separated, quoted or not, with or without a header; date + time + pressure (`'03.11.2026','17:46:00','152.33',min,max,'1'`). The time is read, the reading interval is detected, and the readings are placed by their real times.
- **Reload / append**: dropping the same log again after it has grown matches by clock time: new readings are added, changed ones updated, duplicates never created. Typed readings with no clock times are matched to the file by value. A different gauge's file is detected and replaces instead of overwriting. **Undo last load** button.
- Friendly messages for Excel, PDF or picture files; titles / notes lines in a file are skipped.
- **Drag across the chart** to choose the part of the test to evaluate.

## REV 1.2
- Unlimited readings (hours of 1-minute data). The result is calculated on the **latest N minutes** (N = test length), so a 15-min test that runs for hours is judged on its final 15 minutes.
- **Custom range**: evaluate any portion of the test (From/To minutes, or click a row time; Shift+click for the end).
- Pass/fail now also requires a **decreasing (not worsening) loss-rate trend**, with a configurable tolerance. A rise in pressure is never a failure.
- Max total loss is configurable **per test length** (5 / 10 / 15 / 30 min / custom). Default 75 psi for 15 min.
- Exactly-at-limit behaviour configurable (< or ≤).
- Hours:minutes:seconds time display; scrolling reading list.

## REV 1.1
- Rename to JJ's Pressure Test Analyzer, plain-language running status, improving-trend display, 75 psi cap for 15-min test.
- Audit fixes: float-safe limit comparisons, thousands-separator parsing, 2-decimal rates.

## REV 1.0
- First release: 5/10/15/30 min tests, 1/5/10 min rolling rates, skipped readings supported, downloadable single-file app.
