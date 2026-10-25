# Simbah Cup website

Single-page, mobile-first site for the Simbah Cup cricket tournament (Milton Keynes).

- `index.html` is the whole site. Open it in a browser; no build step.
- `SimbahCup.jpeg` is the original crest. A small copy is already embedded in `index.html`.

## Sections

Indoor Adults, Indoor Seniors, Indoor Juniors (under 15) and Outdoor 2026 (completed). Each has Table, Fixtures, Results and Teams tabs.

## Updating the data

Open `index.html` and find `var COMPS` in the script near the bottom. Each section has:

- `table`: rows of `{ code, name, p, w, l, d, pts, nrr }`
- `fixtures`: `{ home, away, date: "2026-11-01", time: "10:00" }`. Add `r: [homeRuns, homeWkts, awayRuns, awayWkts]` once a match is played and it moves to Results.

Contact details are `EMAIL` and `PHONE` just above `COMPS`.
