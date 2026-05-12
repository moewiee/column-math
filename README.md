# Math Column Practice

A single-page math practice webapp for 1st graders. Generates column-style
addition and subtraction problems, lets the child answer using an on-screen
numpad, then offers a second-try round on the missed problems before showing
worked solutions.

No build step, no dependencies, no backend. Open `index.html` and go.

## Features

- **Question generation** per session, fresh each time. Distribution per
  question: 40% two 2-digit, 40% two 3-digit, 20% mixed (one 2-digit + one
  3-digit). Operation is 50/50 addition / subtraction. Subtraction always
  produces a non-negative result.
- **Session sizes**: 25, 50, or 100 questions.
- **Carry/borrow toggle**: pick "With carry/borrow" (normal — each
  question may or may not require carrying / borrowing) or "Without"
  (every digit pair is guaranteed not to carry on `+` and not to borrow
  on `-`, useful as a first step before introducing regrouping).
- **On-screen numpad** (works on tablet, phone, and desktop). Physical
  keyboard also works — digits, Backspace, Enter, arrow keys.
- **Column-style answer entry**: one box per digit, focus starts at the
  ones place and advances left, matching how column math is performed by
  hand.
- **Two-round flow**:
  1. Answer all questions silently (no per-question feedback).
  2. Score appears; the missed problems are listed (answers hidden) and the
     child re-attempts them.
  3. Final screen shows 1st-try and 2nd-try scores. Only questions still
     wrong after the 2nd attempt are revealed with the correct answer,
     column work (carries / borrows), and a step-by-step explanation.
- **Question bank mode**: skip the practice flow and generate a printable
  list of problems with answers. Toolbar supports regenerate, toggle
  answer key, copy as plain text, and print (with a print-specific
  layout that hides chrome and lays out the grid 4-wide).

## Run it

Open `index.html` in any modern browser. That's it.

```sh
open index.html       # macOS
xdg-open index.html   # Linux
start index.html      # Windows
```

Or serve the directory with any static HTTP server if you prefer
(`python3 -m http.server`, etc.).

## File layout

```
index.html      # the entire app (HTML + CSS + JS, one file)
README.md       # this file
CLAUDE.local.md # local project notes, not checked in
```

## Browser support

Anything that supports ES2020 and CSS Grid. Tested in recent Chrome and
Safari.
