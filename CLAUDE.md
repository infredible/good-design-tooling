# CLAUDE.md

## Purpose

This repo is a curated, opinionated list of tools used for design and development workflows — with a focus on how tooling is shifting in the age of AI-assisted and agentic design processes. It's a living document: tools get added, removed, or re-evaluated as the space evolves.

## Audience

Readers are people in tech who already have hands-on experience designing or building software — designers who write code, developers with strong product sense, or anyone operating at the intersection of both. Do not over-explain foundational concepts (React, CLI usage, component architecture, etc.). Write at the level of someone who knows the tools but may not have tried a specific one yet.

## Tone and language

- Direct and specific. Explain what a tool actually does and why it's worth using, not just what it is.
- Skip marketing language. No "revolutionary", "seamless", or "powerful".
- Use technical vocabulary naturally — CSS selectors, file-based versioning, MCP integration, agentic workflows — without stopping to define them.
- Short sentences. Favor concrete examples over abstract descriptions.
- First-person plural ("we", "our setup") is fine when the framing calls for it.

## Content guidelines

- Each tool entry should cover: what it is, why it fits into an AI-assisted or agentic design workflow, and a minimal getting-started path if one exists.
- Highlight how tools interact with each other where relevant (e.g. Agentation → Claude Code, UIFork + agent-generated variants).
- Avoid bloated CLI reference dumps. Link to docs instead; only include commands that are non-obvious or that illustrate the workflow.
- Keep entries updated as tools evolve. If something is no longer recommended, remove it rather than leaving a stale note.

## Structure

The README is the primary document. Sections:
- **Overview** — one paragraph on what this repo is and who it's for
- **Tools** — apps, libraries, and reference documents used in the workflow
- **Skills** — installable Claude Code skills (`npx skills add`) that shape how an agent approaches UI and frontend work; each entry should note what behavior it instills and how it relates to other entries (e.g. a skill that applies a guidelines doc already listed in Tools)
- **Reading** — articles and courses; lead with the core argument, not a summary
- **To Be Tried** — always the last section; tools that look promising but haven't been used enough to endorse yet
