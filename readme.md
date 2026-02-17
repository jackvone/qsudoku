# QSudoku — Daily Puzzle Website

A daily Sudoku puzzle site with three difficulty levels, motivational quotes, and a clean editorial aesthetic. Ready to deploy to Netlify.

## How It Works

- **No backend required** — all puzzles and quotes are generated deterministically from the current GMT date.
- **Daily reset at GMT midnight** — every day brings 3 new puzzles (Easy / Medium / Hard) and a new quote.
- **Monthly quote themes** — each month has a themed set of 31 quotes (Classic Films, Literature, Science, Ancient Wisdom, Music & Art, Motivational, Sci-Fi, Nature, Anime, Philosophy, Sports Legends, and more). These auto-rotate.
- **Progress saved locally** — completion state is stored in the user's browser localStorage, persisting across sessions for the same day.

## Deploy to Netlify

### Option A — Drag & Drop
1. Zip this folder.
2. Go to [app.netlify.com](https://app.netlify.com) → "Add new site" → "Deploy manually".
3. Drag the zip file onto the upload area.
4. Add your custom domain in Site Settings → Domain Management.

### Option B — GitHub (recommended for updates)
1. Push this folder to a GitHub repository.
2. In Netlify: "Add new site" → "Import an existing project" → Connect GitHub.
3. Leave build settings blank (static site).
4. Deploy!

## Adding Affiliate Discounts (Future)
The sidebar already has a placeholder card labeled **"Special Offers"**. When ready:
1. Replace the placeholder content inside `.affiliate-card .card-body` with your affiliate banner/link/code.
2. Optionally gate it behind puzzle completion by checking `state.quoteUnlocked`.

## Adding / Editing Quotes
All quotes are in `index.html` inside the `MONTHLY_THEMES` array (around line 20).
Each month (index 0–11) maps to a theme with 31 quotes. You can:
- Edit existing quotes
- Add new monthly themes
- Change the theme name

## Puzzle Difficulty
Clue counts can be adjusted in the `CLUE_COUNTS` object:
```js
const CLUE_COUNTS = { easy: 45, medium: 33, hard: 26 };
```
More clues = easier puzzle.

## Files
- `index.html` — entire site (self-contained)
- `netlify.toml` — Netlify deploy config
- `README.md` — this file
