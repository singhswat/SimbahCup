# Simbah Cup website

Mobile-first site for the Simbah Cup cricket tournament (Milton Keynes), with a password-protected admin page.

## Files

- `index.html` is the public site: Indoor Adults, Indoor Seniors, Indoor Juniors (under 15), Outdoor 2026, plus Gallery and Contact. It reads live data from Supabase.
- `admin.html` is the admin page (not linked from the public site, and marked noindex). Use it to add teams and players, enter scores, and upload photos and videos.
- `config.js` holds the Supabase project URL and the public (anon) key. The anon key is safe to publish: row level security means only admins can change anything.
- `SimbahCup.jpeg` is the original crest. A small copy is already embedded in `index.html`.

No build step. Upload all four files to the same folder on your web host (or GitHub Pages).

## Backend

A separate Supabase project called "Simbah Cup" holds the tables `teams`, `players`, `matches`, `gallery` and `admins`, plus a public storage bucket `gallery` for uploads.

- Anyone can read. Only people listed in `admins` (matched by sign-in email) can write.
- Standings are worked out from played matches (win 2 points, tie 1). If a team has a value in Pts on the Teams tab, its typed table figures are used instead. Outdoor 2026 uses typed figures.

## Adding an admin

1. Supabase dashboard, Authentication, Users, Add user: enter the email and a password.
2. SQL editor: `insert into public.admins (email) values ('you@example.com');`
3. Open `admin.html` and sign in.

## Using the admin page

- Teams: pick a section, add teams, edit names, optional manual table figures.
- Players: pick a team, add players with role and shirt number. Each player also has sixes, fours, twos, singles and run-out counts, which feed the Stats page.
- Scores: add a match (home, away, date, time), then enter runs and wickets and save. It moves to Results and the table updates. Clear score puts it back to upcoming.
- Gallery: upload several photos or videos at once. Photos are resized in the browser. Videos up to 50 MB.

- Sponsors: add a sponsor for one event or all events, mark a main sponsor, upload its logo, and add its brands with images. They show in a gold "Presented by" container under each section heading, and on the home page.
- Site: contact email and phone, the home page intro line, an optional notice banner, and the list of admin emails (add or remove people).
- Players, matches and gallery captions can all be edited in place.

Delete buttons need two taps to avoid accidents.

## Juniors

Only show names and photos of under 15s that parents have agreed to.

## Contact details

`EMAIL` and `PHONE` near the top of the script in `index.html`.
