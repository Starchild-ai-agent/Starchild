# We Built Our Codebase for AI Agents

Most teams use AI to write code faster. We did something different. We restructured our entire frontend so that AI agents can own it.

Agent-ready development means a personal AI like Clawdbot or Moltbot can clone our repo and start shipping features. It reads our skills, finds the code, makes changes, and passes our linters.

This is not a gimmick. It is how we think software will be built.

## Why Starchild builds this way

Starchild is intent-driven trading intelligence. Traders describe what they want, AI agents execute. No chart babysitting. No manual order management. Express your intent, let the system handle it.

We realized our development should work the same way. If we are building a product that delegates execution to AI, why build it the old way? The inside should match the outside.

## What we solved

Three problems block agents from working on most codebases:

**Code location.** Agents do not know which file controls a specific button. We built Dev Inspector: click any element, it opens the source file.

**Design to code.** Figma was the gold standard for collaborative design. For agent-ready development, we opted for Pencil because of its MCP capabilities that let it work directly with AI agents and vibe coding workflows.

**Consistency through Skills.** Without explicit rules, every agent writes code differently and your codebase becomes chaos. We built a Skills system: 17 capabilities that teach agents exactly how we do things. Not documentation. Executable knowledge.

### Skills: the secret ingredient

Each skill teaches one thing: how to add an API, how to build a component, how to manage state, how to handle i18n. When an agent needs to add an endpoint, it loads the API skill. When it creates a component, it loads the component skill. The agent absorbs your conventions on the fly, every time.

This is different from a wiki or README. Those explain why. Skills tell agents what to do. Step by step. With examples. Agents do not need to understand your architecture philosophy. They need clear instructions they can follow.

**Result:** Backend engineers, PMs, and designers now contribute frontend code. Not because they learned React. Because agents have what they need to do the work.

## Technical details

### Stack

- React 19 with TypeScript
- Vite for builds
- styled-components for styling
- Redux Toolkit + RTK Query for state management
- wagmi + viem for Web3, with auto-generated contract hooks

### Dev Inspector

A Babel plugin injects file paths at compile time. At runtime, press Shift+Option+C (Mac) to enable click-to-locate mode. Click any element, and it opens the source file in your editor.

The key insight: we filter shared components. Clicking a button opens the business logic that uses the button, not the generic Button.tsx. Context matters.

### Skills system

17+ skills covering: API patterns (RTK Query, injectEndpoints), state management (Redux, persistence, caching), component conventions (structure, typing, examples), internationalization (lingui, Trans component), mobile adaptation (vm function, safe areas), routing and page structure, Web3 contract integration, deployment and CI/CD.

Each skill is structured for agents to parse and follow. Not prose explanations, but actionable instructions with code examples.
