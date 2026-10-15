# AGENTS.md

## Repo shape

- Single-file vanilla JS game: HTML5 canvas, no framework, no bundler, no dependencies.
- Only three runtime files: `index.html`, `game.js`, `favicon.svg`. Everything (input, entities, state machine, loop) lives in `game.js`.
- No `package.json`, no test runner, no linter, no CI. Do not invent `npm test` / `npm run lint` commands or add tooling unless asked.

## Run

Open `index.html` in a browser, or:

```bash
npx serve .
```

No build step. `game.js` is loaded as a classic script (not a module) from `index.html`.

## Code conventions

- `'use strict'` at top; ES6 classes (`Ship`, `Asteroid`, `Bullet`, `Particle`) and top-level mutable game state.
- Input: `keys[code]` is held state; `pressed(code)` is edge-triggered and self-clearing (`justPressed`). Shooting and restart rely on `pressed('Space')` — don't switch to raw `keys` for those.
- All positions wrap toroidally via `wrap(v, max)`; the playfield is fixed at `W=800`, `H=600` (also hardcoded in `index.html` canvas attrs — keep in sync).
- Time step is capped at `0.05s` in `loop()`; update logic is dt-based.

## Doc vs code mismatch

`README.md` claims power-ups and a "estrella fugaz" (shooting star) asteroid type. **Not implemented** in `game.js` — there are no power-up classes or special asteroid types. Trust the code; don't assume these features exist or try to "finish" them unless asked.

## Language

UI strings, HUD text, and comments are in Spanish (`NIVEL`, `PUNTAJE`, section headers). Match that style for new user-facing text in this game unless told otherwise.
