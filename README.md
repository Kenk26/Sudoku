# 🔢 Sudoku

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

A clean, fully playable **Sudoku web app** built with vanilla HTML, CSS, and JavaScript. Features 6 difficulty levels, dark mode, pause/resume, game save/continue, error highlighting, and smooth animations — all with no frameworks or dependencies.

---

## 📸 Preview

<div align="center">
  <table>
    <tr>
      <td><img src="image 1.jpg" width="400"/></td>
      <td><img src="image 2.jpg" width="400"/></td>
    </tr>
  </table>
</div>

---

## ✨ Features

- 🎮 **6 Difficulty Levels** — Easy, Medium, Hard, Very Hard, Insane, Inhuman (29–74 cells removed)
- 🌙 **Dark / Light Mode** — Toggle with one click, preference saved to `localStorage`
- 💾 **Save & Continue** — Game state auto-saved to `localStorage`; resume exactly where you left off
- ⏱️ **Live Timer** — Tracks elapsed time with pause and resume support
- ❌ **Error Highlighting** — Conflicting cells in the same row, column, and 3×3 box turn red with a shake animation
- 🔵 **Smart Cell Hover** — Highlights the entire row, column, and box of the selected cell
- ✅ **Win Detection** — Automatically detects a completed valid grid and shows a results screen
- 📱 **Responsive Design** — Works on both desktop and mobile screens

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Markup | HTML5 |
| Styling | CSS3 (CSS Variables, animations, responsive) |
| Logic | Vanilla JavaScript (ES6+) |
| Font | Google Fonts — Potta One |
| Icons | Boxicons |
| Storage | Browser `localStorage` |

---

## 📁 Project Structure

```
Sudoku/
│
├── index.html        # App structure & screens (start, game, pause, result)
├── style.css         # Full styling with dark mode & animations
├── constant.js       # Game constants (grid size, levels, number list)
├── sudoku.js         # Sudoku generation & validation logic
├── script.js         # UI interactions, game state, events
└── icon.png          # Favicon
```

---

## ⚙️ Installation & Usage

No build tools or install needed — just open in a browser.

### Option 1 — Open Directly

```bash
git clone https://github.com/Kenk26/Sudoku.git
cd Sudoku
# Open index.html in your browser
```

### Option 2 — Live Server (recommended for development)

```bash
# Using VS Code Live Server extension, or:
npx serve .
```

---

## 🚀 How to Play

1. Enter your name in the text field
2. Click the **level button** to cycle through difficulty levels
3. Click **New Game** to generate and start a fresh puzzle
4. Click any empty cell to select it, then click a number (1–9) to fill it
5. **X** button clears the selected cell
6. Errors are highlighted in red — conflicting cells shake to alert you
7. Click the **pause button (⏸)** to pause the timer
8. Complete the grid correctly to see your finish time 🎉

> 💡 If you leave mid-game, click **Continue** next time to resume your saved progress.

---

## 📊 How It Works

```
New Game
    │
    ▼
sudokuCreate() — backtracking algorithm fills a valid 9×9 grid
    │
    ▼
removeCells(grid, level) — randomly removes N cells based on difficulty
    │
    ├── Easy       → 29 cells removed
    ├── Medium     → 38 cells removed
    ├── Hard       → 47 cells removed
    ├── Very Hard  → 56 cells removed
    ├── Insane     → 65 cells removed
    └── Inhuman    → 74 cells removed
    │
    ▼
Player fills cells → checkErr() scans row + col + box for conflicts
    │
    ▼
sudokuCheck() → isFullGrid() → all cells filled with no unassigned → WIN
```

### Sudoku Generation Algorithm

- Uses **recursive backtracking** with a **shuffled number list** to produce a unique, randomized valid grid each game
- `isSafe()` checks row, column, and 3×3 box constraints before placing each number
- Cells are removed randomly based on the selected difficulty level

---

## 💾 localStorage Keys

| Key | Value |
|-----|-------|
| `darkmode` | `true` / `false` |
| `player_name` | Last entered player name |
| `game` | JSON object with full game state (grid, level, timer) |

---

## 🐛 Known Issues / Limitations

- No undo button — mistakes must be cleared manually with the **X** button
- Leaderboard / score history not implemented
- Only one saved game slot (new game overwrites previous save)

---

## 🔮 Future Improvements

- [ ] Undo last move
- [ ] Pencil / notes mode for candidate numbers
- [ ] Hint button (reveal one correct cell)
- [ ] Leaderboard with best times per difficulty
- [ ] Keyboard input support

---

## 👨‍💻 Author

**Ankit Kumar** — [@Kenk26](https://github.com/Kenk26)

---
