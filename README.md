# FIFA World Cup 2026 — Office Sweep HQ ⚽

A single-page live dashboard for the office World Cup sweep. Staff are drawn against
the 48 competing nations; the page tracks live scores, standings, fixtures and
results, and tells you whose country just won.

**Live page:** https://haydos00aoc.github.io/wc2026-sweep/

Built in AOC colours (green `#005058`, gold `#FFE100`). All kick-off times shown in
**AEST (Sydney)**.

---

## What's on the page

| Tab | What it shows |
|-----|---------------|
| 🏆 **Dashboard** | Matches played, latest sweep winner, live count, next/live fixtures, tournament roadmap |
| 📊 **Standings** | Auto-calculated group tables (P / W / D / L / GD / Pts), each team tagged to its staff owner |
| 👥 **Sweep Draw** | All 12 groups with every nation paired to a staff member — searchable |
| 📅 **Schedule** | All 72 group fixtures by day (AEST), plus knockout matches once confirmed — searchable |
| ⚽ **Results** | Live-now and full-time results, with a "who won the points" line per match |

---

## How it works

- **One file.** Everything lives in [`index.html`](index.html) — HTML, CSS and JS, no build step.
- **Live scores.** On open (and every 5 minutes) the page fetches the public ESPN
  World Cup scoreboard feed. Standings and results recalculate automatically from
  completed matches. If the feed is unreachable it shows the last known results.
- **Flags.** Rendered via [Twemoji](https://github.com/twitter/twemoji) (loaded from
  the jsdelivr CDN) so flag emoji display correctly on Windows, which has no native
  flag glyphs. Needs `cdn.jsdelivr.net` to be reachable; if it's ever blocked, flags
  fall back to plain text — the page still works.
- **Hosting.** GitHub Pages, served from `main` / root.

---

## Updating it

1. Edit [`index.html`](index.html) — the sweep draw lives in the `E` object near the
   top of the `<script>` (`"Country": ["flag", "Staff Name", "Group"]`); fixtures are
   in the `M` array below it.
2. Commit and push to `main`:
   ```
   git add index.html
   git commit -m "Update sweep dashboard"
   git push origin main
   ```
3. GitHub Pages rebuilds in ~1 minute. Hard-refresh the page (`Ctrl + F5`) to clear
   the cached version.

To take it down: disable Pages in the repo settings, or delete the repo. Note the
page is public, so cached/indexed copies may persist for a while after removal.

---

*Local preview helper `serve.cjs` is git-ignored and not published.*
