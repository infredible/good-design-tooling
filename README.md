# good-design-tooling

A running list of tools worth using for design and development — with a focus on what's actually shifting as AI-assisted and agentic workflows become the default. Opinionated, not exhaustive. Updated as the space evolves.

Aimed at designers who write code and developers with strong product sense. The basics aren't explained here.

## Tools

### Claude Code + Ghostty

[Claude Code](https://claude.ai/code) is Anthropic's CLI for Claude — runs in your terminal, understands your codebase, and can execute multi-step tasks autonomously. Less "autocomplete in an editor", more "agent that can read, write, and run code across your project."

[Ghostty](https://ghostty.org/) is a native terminal emulator built for performance. The two pair well: Ghostty handles split panes and fast rendering, Claude Code handles the heavy lifting.

### UIFork

[UIFork](https://github.com/sambernhardt/uifork) solves a real friction point in agentic UI work: you can generate a dozen variations with an agent, but switching between them without UIFork means branch-hopping or commenting out code.

It uses file-based versioning — `Button.v1.tsx`, `Button.v2.tsx` — with a floating widget for runtime hot-swapping. Each version is a real file, so agents can generate new ones directly, you can diff them, and promoting a winner is a single command.

```bash
npm install uifork
npx uifork src/components/MyComponent.tsx
npx uifork watch
```

### Agentation

[Agentation](https://www.agentation.com/) is a desktop tool for annotating live UI and passing that context to an agent. You hover over elements, add notes, and get back structured output — CSS selectors, file paths, component hierarchy — that an agent like Claude Code can act on directly.

The MCP integration makes it two-way: the agent can query annotations and respond with updates, so feedback becomes a conversation rather than a one-shot prompt.

### Karpathy-Inspired Claude Code Guidelines

[andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) is a single `CLAUDE.md` file distilled from Andrej Karpathy's observations on where LLM coding agents consistently go wrong — silent assumptions, overcomplicated solutions, touching code they shouldn't.

Four principles: think before coding, simplicity first, surgical changes, goal-driven execution. Drop it into any project and Claude Code will ask before assuming, write less code, and leave unrelated things alone.

```bash
# as a Claude Code plugin (applies across all projects)
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin install andrej-karpathy-skills@karpathy-skills

# or per-project
curl -o CLAUDE.md https://raw.githubusercontent.com/forrestchang/andrej-karpathy-skills/main/CLAUDE.md
```
