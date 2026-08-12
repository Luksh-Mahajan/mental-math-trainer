# Arithmetic Speed Drill

A browser-based mental math trainer designed to improve arithmetic speed through timed practice.

## Overview

Arithmetic Speed Drill is a lightweight, keyboard-first web application inspired by rapid mental-math drills

Users select a time limit, number range, and arithmetic operations, then solve as many problems as possible before time expires. Correct answers are submitted automatically as soon as they are entered.

The benchmark is simple:

> **20 correct problems per minute.**

At the end of each session, the application compares the user's performance against that fixed target.

---

## Features

*  **Timed practice sessions** - 15 seconds to 5 minutes
*  **Basic arithmetic operations** - addition, subtraction, multiplication, and division
*  **Configurable number ranges** - control the difficulty of generated problems
*  **Automatic answer submission** - correct answers immediately advance to the next problem
*  **Keyboard-first interaction** - designed to minimize interruptions while solving
*  **Performance benchmark** - targets 20 correct answers per minute
*  **Goal comparison** - shows whether the user beat or fell short of the target
*  **Responsive interface** — usable on both desktop and mobile

---

## How It Works

### 1. Configure a session

Choose:

* Time limit
* Minimum number
* Maximum number
* Arithmetic operations

### 2. Solve

A problem is displayed and the user enters the answer.

Once the answer matches the correct result, the application immediately:

1. Records the completed problem
2. Updates the score
3. Generates a new problem
4. Clears the input field

No submit button or Enter key is required.

### 3. Review performance

When the timer expires, the application displays:

* **Questions completed**
* **Target for the session**
* How far above or below the target the user finished

The target is calculated as:

```text
Target = 20 × minutes
```

For example:

| Session    | Target |
| ---------- | -----: |
| 15 seconds |      5 |
| 30 seconds |     10 |
| 1 minute   |     20 |
| 2 minutes  |     40 |
| 5 minutes  |    100 |

---

## Problem Generation

Problems are generated dynamically in JavaScript.

### Addition

```text
a + b
```

### Subtraction

Subtraction problems are generated so that the result is non-negative.

```text
a - b
```

### Multiplication

```text
a × b
```

### Division

Division problems are constructed to always produce an integer answer.

The divisor is additionally capped at **12**, keeping division problems appropriate for rapid mental calculation.

```text
a ÷ b
```

where:

```text
1 ≤ b ≤ 12
```

---

## Technical Implementation

The application is intentionally lightweight and requires no backend.

### Technologies

* **HTML5** - application structure
* **CSS3** - responsive interface and layout
* **Vanilla JavaScript** - game state, problem generation, timer, scoring, and interaction
* **GitHub Pages** - static deployment

### Architecture

The application is organized around three primary states:

```text
Settings
   │
   ▼
Game
   │
   ▼
Results
   │
   └──────► Settings
```

Game state is maintained in JavaScript, including:

```javascript
{
    duration,
    remainingTime,
    minNumber,
    maxNumber,
    operations,
    score,
    currentAnswer
}
```

The timer runs independently from problem generation, while the input listener handles answer validation and automatically advances successful answers.

---

## Why I Built It

Fast mental arithmetic is a surprisingly useful skill for quantitative problem solving. Rather than building another static calculator, I wanted to create a tool that emphasizes **speed under time pressure**.

The project also provided a simple way to explore several practical frontend concepts:

* Event-driven programming
* State management
* Dynamic DOM updates
* Randomized problem generation
* Timer-based application logic
* Input validation
* Responsive UI design

---

## Running Locally

No installation or build process is required.

```bash
git clone https://github.com/YOUR_USERNAME/arithmetic-speed-drill.git
cd arithmetic-speed-drill
```

Then open:

```text
index.html
```

in a browser.

---

## Deployment

The application can be deployed directly through **GitHub Pages** because it is a fully static website.

Repository:

```text
arithmetic-speed-drill/
└── index.html
```

---

## Future Improvements

Potential extensions include:

* Personal best tracking with `localStorage`
* Difficulty presets for quantitative interview preparation
* Historical performance graphs
* More advanced problem types
* Custom session lengths
* Streak tracking
* Separate difficulty levels
* More granular arithmetic controls
* Mobile-specific keyboard optimizations

---

## License

This project is available for personal and educational use.
