# Darts Scorer

A self-contained darts scoring app for classic X01 games. No build step, no
dependencies — just open `index.html` in a browser.

## Features

- **301 / 501 / 701** game modes
- **1–4 players** with custom names
- **Double-out or straight-out** finish rules
- **Per-dart entry**: pick Single / Double / Treble, then tap the number
  (25 and bullseye supported; the multiplier resets to Single after each dart)
- **Bust detection**: going below zero, leaving 1, or finishing without a
  double (in double-out mode) restores the score to the start of the turn
- **Checkout suggestions** for any finishable score up to 170
- **Undo** any dart
- **Live stats**: 3-dart average, darts thrown, and legs won per player
- Legs alternate the starting thrower automatically

## Usage

Open `index.html` directly, or serve it:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Rules implemented

Standard X01: each player starts on the chosen total and subtracts what they
score with up to three darts per turn. In double-out mode the final dart must
land on a double (or the bullseye) to win the leg, and a turn that leaves a
score of 1 or below 0 — or reaches exactly 0 without a double — is a bust,
restoring the score the player had at the start of the turn.
