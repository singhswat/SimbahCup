# Simbah Cup website

Mobile-first site for the Simbah Cup cricket tournament (Milton Keynes). No database and no sign-up for visitors: everything is plain files in this repo.

## Files

- `index.html` is the public site: Indoor Adults, Seniors, Juniors (under 15), Outdoor 2026, Stats, Gallery and Contact.
- `admin.html` is the admin page (not linked from the site, marked noindex).
- `data/site.json` holds teams, players, sponsors, rules, gallery list and site text.
- `data/YYYY-MM-DD.json` is one file per match day: the matches, scores, bonus points and each player's sixes, fours, twos, singles and run outs for that day. `site.json` lists the match days in `sundays`.
- `gallery/` and `sponsors/` hold uploaded photos, videos and logos.
- `SimbahCup.jpeg` is the original crest. A small copy is embedded in `index.html`.

The site reads these files each time it opens and works out the tables and player stats itself (win 2 points, tie 1; Juniors use the U15 rules: win 6, tie 3, plus bonus points).

## Hosting

GitHub Pages: repo Settings, Pages, deploy from branch `main`, folder `/ (root)`. The site is then at `https://singhswat.github.io/SimbahCup/`. After a change is saved it shows within a couple of minutes.

## Using the admin page

1. Open `admin.html` on the site. Enter the repo (`singhswat/SimbahCup`), branch `main` and an access token. The token is only kept in that browser.
2. Make changes in any tab. Nothing goes live until you press **Save to website** at the bottom. That saves the changed files to GitHub.
3. Tabs: Matches (pick a match day, add matches, type scores, bonus points and player shots), Teams (teams and players), Gallery, Sponsors, Rules, Site (contact details, notice banner, knockouts, venue).

Making a token: GitHub, Settings, Developer settings, Personal access tokens, Fine-grained tokens, Generate. Pick only this repository and give it **Contents: Read and write**. Give a separate token to each person so one can be removed without affecting the others. Anyone with a token can change the site.

## Things to know

- Each match day is its own file, so two people entering scores for different days never clash. If two people save the same file, the second sees a message and must reload.
- Player shots are counted by player name. If you rename a player, shots entered under the old name no longer count.
- Net run rate and the head-to-head tie-break are not worked out automatically. Ties on points are ordered by wins.
- Only show names and photos of under 15s that parents have agreed to.
