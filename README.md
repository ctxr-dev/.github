# ctxr-dev: start here

Composable tools for building with AI coding agents (Claude Code, Codex, Cursor, any MCP client).
Install only what you need. This page tells you what to pick and where to go.

## Start

1. **Get the installer.** `npx @ctxr/kit install <name>` is how you add every skill and agent below. No global install. ([kit](https://github.com/ctxr-dev/kit))
2. **Pick a memory backend.** One choice, Wiki or RAG, covered next. This is the decision that matters most.
3. **Add the skills you need.** Code review fits almost everyone; the rest are by need (table below).

On a team that tracks work in GitHub? Also add the workflow stack (methodology + GitHub MCP, and the staff-engineer agent to automate it).

## Pick your memory

Self-improving memory: your agent recalls past lessons before it works, and saves a new one the moment
you correct it, so the same mistake does not recur. Both options expose the same tools and the same
behavior, so you can switch later. Install one, not both.

|  | Wiki | RAG |
| --- | --- | --- |
| Repo | [`llm-wiki-memory`](https://github.com/ctxr-dev/llm-wiki-memory) | [`@ctxr/memory`](https://github.com/ctxr-dev/memory) |
| Stores memory as | git-versioned markdown in your repo | a local Dify vector store |
| Infrastructure | none (Node + git) | Docker + Dify |
| **Best for** | solo, small, and medium projects; offline; low overhead | large corpora; teams; retrieval precision at scale |

**Default to Wiki.** Choose RAG when the corpus is large, several people or agents share one store, or
Docker is already in your stack.

Each repo ships a one-prompt AI install: you paste a short prompt into your agent and it does the clone,
bootstrap, and wiring for you. Start there, do not hand-assemble it:

- Wiki, no Docker: **[github.com/ctxr-dev/llm-wiki-memory#install](https://github.com/ctxr-dev/llm-wiki-memory#install)**
- RAG, Docker + Dify: **[github.com/ctxr-dev/memory#install](https://github.com/ctxr-dev/memory#install)**

Not ready for persistent memory? Skip it. Nothing else depends on it.

## Everything in the toolkit

| Component | Use it to | Get it |
|---|---|---|
| [`@ctxr/kit`](https://github.com/ctxr-dev/kit) | install, update, and scaffold skills and agents | `npx @ctxr/kit` |
| [`llm-wiki-memory`](https://github.com/ctxr-dev/llm-wiki-memory) | zero-infra, git-versioned agent memory | [install guide](https://github.com/ctxr-dev/llm-wiki-memory#install) |
| [`@ctxr/memory`](https://github.com/ctxr-dev/memory) | RAG agent memory (Dify) for scale | [install guide](https://github.com/ctxr-dev/memory#install) |
| [`@ctxr/skill-code-review`](https://github.com/ctxr-dev/skill-code-review) | multi-specialist review with a GO / NO-GO verdict | `npx @ctxr/kit install @ctxr/skill-code-review` |
| [`@ctxr/skill-frontend-excellence`](https://github.com/ctxr-dev/skill-frontend-excellence) | ship fast, accessible, distinctive web UI | `npx @ctxr/kit install @ctxr/skill-frontend-excellence` |
| [`@ctxr/skill-llm-wiki`](https://github.com/ctxr-dev/skill-llm-wiki) | make your agent read docs and code token-efficiently | `npx @ctxr/kit install @ctxr/skill-llm-wiki` |
| [`github-dev-methodology`](https://github.com/ctxr-dev/github-dev-methodology) | a consistent GitHub issue and PR workflow, plus subagent orchestration | [read the methodology](https://github.com/ctxr-dev/github-dev-methodology) |
| [`@ctxr/mcp-github`](https://github.com/ctxr-dev/mcp-github) | structured GitHub tool calls instead of `gh` shell-outs | [setup](https://github.com/ctxr-dev/mcp-github#use-as-an-mcp-server) |
| [`@ctxr/agent-staff-engineer`](https://github.com/ctxr-dev/agent-staff-engineer) | drive a ticket to an open PR, then hand off before merge | `npx @ctxr/kit install @ctxr/agent-staff-engineer` |
| [`@ctxr/fsm`](https://github.com/ctxr-dev/fsm) | author your own deterministic multi-agent workflow | [docs](https://github.com/ctxr-dev/fsm) |

## Starter stacks

- **Solo or side project:** kit + Wiki memory + code-review. Add frontend-excellence if you ship web UI.
- **Small team on GitHub:** the above + methodology (start at the `pr-only` preset) + GitHub MCP.
- **Larger team:** RAG memory + code-review + agent-staff-engineer + methodology (`full` preset) + GitHub MCP.

All MIT licensed, developed in the open at [github.com/ctxr-dev](https://github.com/ctxr-dev).
