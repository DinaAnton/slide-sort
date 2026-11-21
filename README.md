# Slide \& Sort

A drag-anywhere color-matching puzzle for the browser and mobile home screen.

Bricks fill a grid with a handful of open gaps. Drag any brick freely across
those open squares — up, down, sideways, or diagonally, through as many empty
cells as the space allows — just like sliding a tile with your finger. Get a
connected chain of same-color bricks to reach its matching gate on the edge
of the board, and the whole chain clears out together. Clear every brick to
finish the level; six levels ramp up in board size and color count.

## Features

* **Freeform drag movement** — no fixed directions or turn-based steps; bricks
slide through any reachable open space, including diagonally.
* **Procedurally generated levels** — every level (and every replay of a
level) is freshly generated, always guaranteed solvable, so no two runs are
identical.
* **Six levels** of increasing board size and color variety.
* **Move counter and personal best** — tracks the fewest moves used to clear
a full run, saved locally on-device.
* **Procedural audio** — sound effects and a gentle ambient music loop are
synthesized in-browser (Web Audio API); no audio files required.
* **Installable PWA** — add it to your phone's home screen and play offline,
no app store required.
* **Light/dark theme aware**, fully responsive, single-file game engine.

## Playing it

Just open `index.html` in any modern browser (desktop or mobile). No build
step, no server required for a quick try — though installing as a PWA (see
below) needs the files to be served over `http(s)`.

## Installing as a PWA

1. Serve this folder over HTTPS (or `http://localhost` during development —
browsers treat localhost as a secure context). Any static file host
works: GitHub Pages, Vercel, Netlify, Cloudflare Pages, or a simple local
server such as `npx serve` or `python3 -m http.server`.
2. Open the hosted URL on your phone in Chrome or Safari.
3. Use the browser menu and choose **"Add to Home Screen"** (iOS Safari) or
**"Install app"** (Android Chrome).
4. The game launches full-screen from your home screen icon, and keeps
working offline afterwards thanks to the included service worker.

## Project structure

```
.
├── index.html              # the entire game: markup, styles, and logic
├── manifest.json           # PWA metadata (name, icons, theme colors)
├── service-worker.js       # offline caching for the app shell
├── icons/
│   ├── icon-192.png        # home-screen icon (standard + maskable)
│   ├── icon-512.png        # home-screen icon (standard + maskable)
│   ├── apple-touch-icon.png
│   └── favicon-32.png
└── README.md
```

## Tech notes

The whole game is a single self-contained HTML file — vanilla JavaScript,
no build tools, no external runtime dependencies, and no backend. Levels are
generated with a territory-growth algorithm (a multi-source flood fill from
border seed cells) and then scrambled with a sequence of legal moves, which
guarantees every generated level is solvable. Fonts are loaded from Google
Fonts; everything else is inline.

## About this project

Slide \& Sort is an original game concept, designed and directed by
me (the designer), built through an iterative "vibe coding" collaboration
with an AI coding assistant (Claude, by Anthropic). The gameplay idea,
creative direction, and every round of playtesting feedback that shaped the
mechanics — from the color-matching rules to the free drag-anywhere
movement — came from the designer; the AI assisted with implementation,
debugging, and polish along the way.

## License

All rights reserved by the project's creator, unless you choose to license
it otherwise (for example, MIT or CC BY-NC) before sharing it publicly.

