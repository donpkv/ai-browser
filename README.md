# AI Browser

An AI-oriented web browser built from scratch as a learning project.

## What this is

A hybrid browser combining two rendering approaches:

- **Chromium tabs** (via Electron) for browsing real websites day-to-day
- **Custom Rust rendering engine** (built from scratch) for learning how browsers actually work
- **AI sidebar** that can chat about the current page using a local or cloud LLM
- **Knowledge Mode** that ingests visited pages into a vector database, enabling RAG-powered Q&A across your entire browsing history

## Tech stack

| Layer | Tech |
|---|---|
| Shell | Electron |
| UI | Angular 18 + TypeScript + Tailwind CSS |
| Custom engine | Rust (html5ever, cssparser, taffy, tiny-skia) via napi-rs |
| Knowledge Service | FastAPI (Python) |
| Vector DB | Qdrant |
| LLM | Ollama (local) + optional OpenAI/Anthropic |
| Metadata DB | SQLite |
| Packaging | electron-builder |

## How it's being built

Many small phases (60-100 total). Each phase introduces one concept, produces a few files, and ends with one git commit. Every phase is explained in a `docs/phaseX-Y-title.md` file before any code is written.

## Current status

Phase 0 — tooling and repo setup.
