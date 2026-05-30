# Phase 1.0 — Create electron-app/, install Electron

## What is Electron?

Electron is a framework for building desktop applications using web technologies (HTML, CSS, JavaScript). It works by bundling Chromium (Chrome's rendering engine) and Node.js into a single executable.

Apps built with Electron: VS Code, Slack, Discord, Notion, Figma, GitHub Desktop, Microsoft Teams, 1Password, Obsidian, Cursor.

## Why Electron for this project?

We're building a browser. We need Chromium anyway (for the "Normal" tabs that browse real websites). Electron gives us Chromium bundled in, plus Node.js for system access (file I/O, LLM API calls, SQLite), plus a cross-platform window — all in one package.

Our Rust rendering engine (Phase 7+) will power "Custom Engine" tabs for learning purposes, but it won't be able to render complex modern websites. Chromium handles those.

## Two-process architecture

- **Main process** (one per app): runs Node.js, controls app lifecycle, creates windows, has full OS access.
- **Renderer process** (one per window): runs Chromium, renders HTML/CSS/JS, sandboxed by default — no Node.js access for security.

## What we did

1. Created `electron-app/` folder with its own `package.json`.
2. Set `"main": "main.js"` — tells Electron which file to run as the main process entry point.
3. Set `"scripts": { "start": "electron ." }` — so `npm start` launches the app.
4. Ran `npm install electron --save-dev --workspace=electron-app` — installed Electron 42.3.0 (Chromium 134, Node 22).
5. Verified with `electron --version` -> v42.3.0.

## What's next

Phase 1.1: write `main.js` that actually opens a window.
