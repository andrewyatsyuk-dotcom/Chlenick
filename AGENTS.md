# AGENTS.md

## Cursor Cloud specific instructions

This is a single-file static HTML project (`index.html`) — a Telegram Mini App bakery/clicker game. There is no build system, no package manager, no dependencies, no tests, and no linter.

### Running the application

Serve `index.html` with any static HTTP server. Example:

```sh
python3 -m http.server 8080 --directory /workspace
```

Then open `http://localhost:8080/index.html` in a browser.

### Key notes

- The entire app lives in `index.html` (~1160 lines of inline HTML/CSS/JS).
- The game uses Firebase Realtime Database for cloud saves, leaderboard, marketplace, and gifts — the Firebase URL is hardcoded and already hosted externally. No local Firebase setup needed.
- Telegram WebApp integration (user identity, haptic feedback) only works inside the Telegram app. Outside Telegram, the game runs in anonymous mode with an `anon_*` user ID.
- Game state persists in `localStorage` under the key `bakery_game_v2`.
- There are no automated tests, no linter config, and no build step to run.
