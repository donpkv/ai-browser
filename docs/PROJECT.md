# AI Browser — Project Documentation

## Overview

An AI-oriented web browser built from scratch as a learning project. Combines an Electron desktop shell with a hand-written Rust rendering engine and a Knowledge Mode backed by a FastAPI RAG service.

## Tech Stack

| Layer | Tech | Why |
|---|---|---|
| Shell | Electron | Bundles Chromium + Node.js; same engine for app UI and browser tabs |
| UI | Angular 18 + TypeScript + Tailwind | Standalone components + signals; enterprise structure |
| Custom engine | Rust via napi-rs | html5ever, cssparser, taffy, tiny-skia; learn how browsers actually work |
| Knowledge Service | FastAPI (Python) | Lightweight RAG backend; rich LLM/embedding library ecosystem |
| Vector DB | Qdrant | Familiar from local-ai-orchestrator; fast semantic search |
| LLM | Ollama (local) + optional cloud | Mistral 7B default; OpenAI/Anthropic via env config |
| Metadata DB | SQLite via better-sqlite3 | Single file, no separate process, perfect for a desktop app |
| Credentials | Electron safeStorage | OS keychain (DPAPI on Windows) |
| Packaging | electron-builder | Produces .exe, .dmg, .AppImage |

## Phase Progress

| Phase | Title | Status |
|---|---|---|
| 0.0 | git init with .gitignore | done |
| 0.1 | add README.md | done |
| 0.2 | add .env and .env.example | done |
| 0.3 | add subtasks.json | done |
| 0.4 | add root package.json with npm workspaces | done |
| 0.5 | add docs/ with PROJECT.md | done |
| 1.0 | create electron-app/, install Electron | planned |
| 1.1 | main.js opens an empty BrowserWindow | planned |
| 1.2 | preload.js + contextBridge | planned |
| 1.3 | Angular CLI scaffold | planned |
| 1.4 | TypeScript inside Angular (concepts doc) | planned |
| 1.5 | Angular signals (concepts doc) | planned |
| 1.6 | Tailwind CSS setup inside Angular | planned |
| 1.7 | Electron-Angular dev/prod loader | planned |
| 1.8 | Hello AI Browser end-to-end | planned |

## Folder Structure

```
ai-browser/
|-- .gitignore
|-- .env                  secrets (gitignored)
|-- .env.example          template
|-- README.md
|-- package.json          npm workspace root
|-- subtasks.json         phase registry
|-- docs/
|   |-- PROJECT.md        this file
|-- electron-app/         (Phase 1+)
|-- rust-engine/          (Phase 7+)
|-- knowledge-service/    (Phase 18+)
```

## Conventions

- C19: Explanation-first — explain concepts before writing code
- C20: Micro-phases — 1-3 files and 10-80 lines per phase
- C21: One commit per phase — `Phase X.Y: <title>`
- All conventions C1-C18 from local-ai-orchestrator also apply
