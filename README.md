# Roulette Lab

A single-file roulette strategy analysis and backtesting tool. Load your spin history, place chips on the visual table, and instantly see how your bet performs. A built-in algorithm can suggest and auto-place the optimal bet based on sector analysis or statistical edge.

**[Live Demo →](https://kobil dn.github.io/RouletteLab)**

---

## Features

### Visual Roulette Table
- Full CSS Grid table — straight, split, and corner inside bets, plus all outside bets (dozens, columns, red/black, even/odd, high/low)
- Ghost chip preview on hover; right-click to remove
- 7 chip denominations ($0.10 – $20) with distinct colours and stack badges
- Chip drop animation on placement

### Spin History Input
- **Manual** — paste any list of numbers 0–36 with any delimiter (space, comma, dot, pipe, etc.)
- **OCR** — upload a screenshot of your spin history; Tesseract.js reads the numbers automatically via canvas preprocessing and row detection
- **Keypad** — 37 on-screen buttons (0–36) for live entry
- Configurable spin window (last N rounds)

### Best Bet Engine
Three output types — **Best Coins** (straight-up), **Best Splits**, **Best Corners** — with two algorithm modes:

| Mode | Logic |
|------|-------|
| **Sector** | Scores the three classic wheel sectors (Voisins du Zéro, Tiers du Cylindre, Orphelins). Hottest sector gets the coins. Falls back to arc mode (highest-density N-neighbor arc on the physical wheel). |
| **Stats** | Scores every number 0–36 by summing category edges (red/black, even/odd, low/high, dozens, columns, zero) plus individual frequency. Greedy deduplication ensures no number appears in more than one bet unit. |

- **Default Shift** — rotate all placements ±N positions around the physical wheel order
- **Auto-Update** toggle — re-places best coins automatically on every new round

### P&L Backtester
Replays your entire chip layout against every spin in history:
- Straight 35:1 · Split 17:1 · Corner 8:1
- Dozens/Columns 2:1 · Red/Black/Even/Odd/High/Low 1:1
- Reports: coins/round, stake/round, total rounds, total staked, total returned, net P&L
- Coin value override mode for uniform-unit analysis

### Live Stats Sidebar
Updates with every new round:
- Red/Black, Even/Odd, Low/High percentages with bar charts
- Dozen and column breakdown
- Zero frequency
- 8-card heat panel — top frequency zones with rank dots, heat bars, and hit counts

### Pattern Management
- 10 named save slots (localStorage)
- Stores full chip placement map + outside bet map
- Save, rename, and restore instantly

---

## Usage

1. Open `index.html` in any modern browser — no install, no server needed
2. Enter spin results in the input field (or upload a screenshot for OCR)
3. Place chips on the table, or click **Best Coins / Best Splits / Best Corners** to auto-place
4. Check the P&L panel to see how your bet performs against the history
5. Save your setup as a named pattern for later

---

## Tech

- Vanilla JavaScript — no frameworks or build step
- Single self-contained HTML file
- [Tesseract.js v5](https://github.com/naptha/tesseract.js) for OCR (loaded from CDN)
- Google Fonts: Cinzel + Share Tech Mono
- localStorage for pattern persistence

---

## Changelog

See the changelog section inside the app for full version history.

Current version: **v5.1**

---

## License

MIT
