# good-design-tooling

A running list of tools worth using for design and development — with a focus on what's actually shifting as AI-assisted and agentic workflows become the default. Opinionated, not exhaustive. Updated as the space evolves.

Aimed at designers who write code and developers with strong product sense. The basics aren't explained here.

## Tools

### Claude Code + Ghostty

[Claude Code](https://claude.ai/code) is Anthropic's CLI for Claude — runs in your terminal, understands your codebase, and can execute multi-step tasks autonomously. Less "autocomplete in an editor", more "agent that can read, write, and run code across your project."

[Ghostty](https://ghostty.org/) is a native terminal emulator built for performance. The two pair well: Ghostty handles split panes and fast rendering, Claude Code handles the heavy lifting.

**Audio notifications when Claude Code finishes:** Claude Code supports hooks that fire on events. Add a `Notification` hook to `~/.claude/settings.json` to play a sound when it completes a task and hands control back to you — useful when running longer agentic tasks in the background.

```json
{
  "hooks": {
    "Notification": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "afplay /System/Library/Sounds/Glass.aiff"
          }
        ]
      }
    ]
  }
}
```

Swap `Glass.aiff` for any file in `/System/Library/Sounds/` — `Ping.aiff`, `Funk.aiff`, etc.

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

### Rauno's Web Interface Guidelines

[interfaces](https://github.com/raunofreiberg/interfaces) by Rauno Freiberg is a living document of specific, opinionated details that separate good web UIs from mediocre ones — covering interactivity, typography, motion, touch, performance, and accessibility. Less "follow WCAG" and more "don't let hover states fire on touch press."

Worth keeping close when building with an agent: paste the relevant sections into a `CLAUDE.md` as project rules, or convert them into a Claude Code skill so they apply across projects. Either way, it gives an agent precise, checkable criteria rather than vague design direction.

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

## Reading

Pieces worth sitting with — on craft, quality, and what design actually means as the tools around it keep changing.

- [Design is more than code](https://linear.app/now/design-is-more-than-code) — Karri Saarinen on why the "should designers code" debate misses the point. The real question is whether you're doing the upstream work: understanding the problem, forming a concept, then executing. Tools and mediums are secondary.

- [Output isn't design](https://linear.app/now/output-isn-t-design) — Design is the search for fit between a form and its context. AI tools that generate polished-looking interfaces don't resolve the underlying tensions — they just make it easier to confuse production with problem-solving.

- [Why is quality so rare?](https://linear.app/now/why-is-quality-so-rare) — Karri Saarinen on the recurring cycle where new technology enables quality work, then gradually optimizes it away. Quality is a choice, requires taste, and — contrary to the usual assumption — is good business strategy.

- [Family Values](https://benji.org/family-values) — A close read of how the Family crypto wallet achieves its feel through three principles: simplicity via gradual revelation, fluidity through transitions that give the interface physical rules, and delight placed deliberately where it has the most impact.

## To Be Tried

### Conductor

[Conductor](https://www.conductor.build/) is a macOS app for running multiple AI coding agents in parallel — Claude Code and Codex — each in isolated workspaces. Think of it as a management layer: spin up several agents on different tasks simultaneously, review their changes, then merge selectively. Potentially useful for parallelizing design iterations or running agents on independent parts of a project at once.
