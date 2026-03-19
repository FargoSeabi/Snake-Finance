# 🐍 Snake Finance

> **A retro-cyberpunk snake game where eating coins triggers finance quiz questions. Answer correctly to grow. Answer wrong and watch your snake shrink — one segment at a time.**

---

## 📸 Overview

Snake Finance is a browser-based educational game that combines the classic Snake mechanic with personal finance trivia. It runs entirely in a single HTML file — no dependencies, no install, no server required.

---

## 🎮 How to Play

1. Open `snake-finance.html` in any modern browser.
2. Use the **arrow keys** to steer your snake toward the golden **$** coin.
3. When you eat a coin, a **Q-Card** flips up with a finance question.
4. Select your answer by clicking or pressing **1**, **2**, or **3**.
5. Correct answer → snake **grows** by 2 segments and you earn XP.
6. Wrong answer → snake **shrinks** by 3 segments with a red burst animation.
7. Avoid running into yourself. The snake wraps around the walls.

---

## ⌨️ Controls

| Key | Action |
|---|---|
| `↑ ↓ ← →` | Steer the snake |
| `1` / `2` / `3` | Answer the current question |
| `P` | Pause / unpause |

---

## 📊 Scoring & Progression

| Event | Effect |
|---|---|
| Eat a coin | +100 score |
| Correct answer | +2 snake segments, +120 XP |
| Wrong answer | −3 snake segments |
| XP threshold reached | Level up |

XP needed to level up scales with your current level: `level × 360 XP`.

---

## 💡 Finance Topics Covered

The quiz draws from a pool of 10 personal finance questions covering:

- Saving vs spending
- What a loan is and how it works
- Budgeting habits
- Compound interest
- Emergency funds
- Debt repayment strategies
- Investment diversification
- Net worth calculation
- Fixed vs variable expenses

---

## ✨ Features

**Gameplay**
- Smooth canvas-based rendering at 60 fps
- Wall wrapping (no instant wall deaths)
- Self-collision game over
- Staggered shrink animation with red particle bursts on wrong answers

**UI**
- Cyberpunk dark theme with scanline overlay and ambient glow
- Animated Q-Cards that fly in with a 3D spring entrance and slide out on dismiss
- Holographic shimmer stripe on each Q-Card
- Live sidebar: Score, Level + XP bar, Accuracy bar, Snake Length
- Scrolling finance tips ticker at the bottom of the screen
- Full Game Over screen with session stats

---

## 🗂️ File Structure

```
snake-finance.html    ← The entire game (single self-contained file)
README.md             ← This file
```

---

## 🛠️ Customisation

**Adding questions** — find the `questions` array in the `<script>` block:

```js
const questions = [
  { q: "Your question here?", opts: ["Option A", "Option B", "Option C"], ans: 0 },
  //                                                                        ↑ index of correct answer
];
```

**Game speed** — change the interval in `initGame()`:

```js
gameLoopId = setInterval(tick, 160); // lower = faster
```

**Shrink amount** — in `answerQuestion()`:

```js
animateShrink(3); // change 3 to shrink more or fewer segments
```

**XP per correct answer** — in `answerQuestion()`:

```js
xp += 120; // increase for faster levelling
```

---

## 🌐 Browser Compatibility

Works in any modern browser that supports the HTML5 Canvas API:

- Chrome / Edge 90+
- Firefox 88+
- Safari 14+

No internet connection required after the page loads (Google Fonts are fetched once on first load for the Orbitron and Share Tech Mono typefaces).

---

## 📄 License

Free to use, modify, and distribute for educational purposes.
