---
name: toastmasters-timer
description: A self-contained single-file HTML/JS Toastmasters Club Timer.
metadata: {}
version: 1.0.0
---

# Toastmasters Timer

A standalone `toastmasters-timer.html` file that runs entirely in the browser. Open it from your filesystem — no internet connection needed during use.

## Files

- `index.html`: The local entry point that loads the script.
- `index.js`: Returns the webview URL pointing to the GitHub-hosted UI.

## Prompts / Triggers

- "Open virtual piano"
- "Play the piano"
- "I want to play piano"
- "Show me a piano keyboard"

## Instructions

Call the `run_js` tool

## Features

## What This Is

A standalone `toastmasters-timer.html` file that runs entirely in the browser. Open it from your filesystem — no internet connection needed during use.

## Features

| Feature | Detail |
|---|---|
| **Presets** | Ice Breaker (4–6 min), Prepared Speech (5–7 min), Evaluation (2–3 min), Custom |
| **Traffic Lights** | Green, Yellow, Red — light up at configured timestamps |
| **Bell Rings** | Web Audio API synthesized bell; configurable at each light change |
| **Overtime Bell** | Configurable number of rings (default 2) at overtime threshold |
| **Progress Bar** | Visual progress arc between each phase |
| **Bell Tuning** | Frequency (Hz), decay length, and volume all adjustable |
| **Keyboard** | `Space` = Start/Pause, `R` = Reset |

## Default Timings

| Preset | Green | Yellow | Red | Overtime |
|---|---|---|---|---|
| Ice Breaker | 4:00 | 5:00 | 6:00 | 7:00 |
| Prepared Speech | 5:00 | 6:00 | 7:00 | 8:00 |
| Evaluation | 2:00 | 2:30 | 3:00 | 3:30 |
| Custom | user-defined | — | — | — |

## Bell Behaviour

- 1 ring when the **Green** light turns on (minimum time reached)
- 1 ring when the **Yellow** light turns on (approaching maximum)
- 1 ring when the **Red** light turns on (at maximum time)
- N rings (default 2) when the **Overtime** threshold is passed

Each bell event can be individually enabled/disabled via the Settings panel.

## Customization via Settings Panel

Click ⚙ Settings to expand:

- **Light Timing** — set minutes and seconds for each threshold
- **Bell Settings** — toggle bells per phase, set overtime ring count
- **Volume** — 0–100%
- **Tone (Hz)** — 300–1400 Hz (default 880 Hz = A5, warm bell sound)
- **Decay** — 0.5s–3.0s (how long each ring sustains)

## How to Use It

1. Open `toastmasters-timer.html` in Chrome, Firefox, Safari, or Edge
2. Select a speech preset
3. Click **Start** (or press `Space`)
4. Lights illuminate and bells ring automatically at configured times
5. Click **Reset** (or press `R`) to start again

## Modifying the HTML

To change default presets, edit the `PRESETS` object in the `<script>` section:

```js
const PRESETS = {
  icebreaker:  { g: [4,0],  y: [5,0],  r: [6,0],  o: [7,0]  },
  prepared:    { g: [5,0],  y: [6,0],  r: [7,0],  o: [8,0]  },
  evaluation:  { g: [2,0],  y: [2,30], r: [3,0],  o: [3,30] },
  custom:      { g: [4,0],  y: [5,0],  r: [6,0],  o: [7,0]  }
};
```

Format: `[minutes, seconds]`

## When to Ask Claude to Regenerate

- Add a countdown mode (count down from max time to 0)
- Add a speaker name / speech title input
- Export timing logs as CSV
- Add a Sergeant-at-Arms mode with consecutive speech slots
- Dark/light theme toggle
- Multi-language labels
