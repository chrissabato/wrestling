# Wrestling Results Viewer

A single-page site that turns a TrackWrestling results CSV into a readable
per-wrestler listing: weight class → wrestler → each match in order
(round, win type, score/time, opponent), plus their finish.

## Use it

- Open `index.html` and drag a CSV onto the page (or click "choose a file").
  Nothing is uploaded — the file is read in your browser.
- Or put a CSV next to `index.html` and link to it:
  `https://<user>.github.io/<repo>/?csv=sample.csv`

Filter by weight, team, name, or "placers only". The Print button gives a clean printout.

## Host on GitHub Pages

1. Create a repo and push `index.html` (plus any CSVs you want to link to).
2. In the repo: **Settings → Pages → Source: Deploy from a branch**, pick `main` / root.
3. The site appears at `https://<user>.github.io/<repo>/` within a minute or two.

## CSV format

Expects TrackWrestling's export columns (the `="..."` Excel quoting is handled):
`Date, Weight, Round, Winning Wrestler, Winning Team, Result, Win Type, Losing Wrestler, Losing Team, City, State, Event`

Finish is worked out from the placement matches (e.g. winning the "3rd Place Match" = 3rd).
If a placement match isn't in the file, the page infers the range (e.g. "1st–2nd")
from which rounds fed into placement matches at other weights. Matches are listed
in the order they appear in the file.
