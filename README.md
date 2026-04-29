# good-design-tooling

> A collection of tools for good design.

## Overview

_TODO: describe what this project does._

## Getting Started

_TODO: add setup and usage instructions._

## Tools

### Claude Code + Ghostty

[Claude Code](https://claude.ai/code) is Anthropic's official CLI for Claude — an agentic coding tool that runs in the terminal. [Ghostty](https://ghostty.org/) is a fast, native terminal emulator that pairs well with Claude Code for an AI-assisted development workflow.

### UIFork

[UIFork](https://github.com/sambernhardt/uifork) is a dev tool for exploring UI variations directly inside your React app. It uses file-based component versioning (`Button.v1.tsx`, `Button.v2.tsx`, ...) and runtime hot-swapping so you can flip between alternatives instantly — no reloads, no branch changes. AI-friendly by design: each version is a separate file, making it easy to generate alternatives with an agent.

```bash
npm install uifork
npx uifork src/components/MyComponent.tsx
npx uifork watch
```

### Agentation

[Agentation](https://www.agentation.com/) is a desktop tool for annotating UI elements and passing structured context to AI coding agents. You click elements on a live webpage, add notes, and generate output (CSS selectors, file paths, component hierarchy, styling info) that can be dropped into Claude Code, Cursor, or any agent. Supports MCP integration for real-time sync, turning design feedback into an interactive conversation.

## Contributing

_TODO: add contribution guidelines._
