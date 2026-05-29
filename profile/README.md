<!--
  ctxr-dev org profile.

  GitHub renders this file at https://github.com/ctxr-dev because it
  lives at `profile/README.md` inside the org's `.github` repo. Edit
  it the same way you edit any README; changes propagate to the org
  landing page on the next page load.
-->

<div align="center">

<a href="https://github.com/ctxr-dev">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,2,8,20,30&height=220&section=header&text=ctxr-dev&fontSize=80&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Composable%20tools%20for%20AI%20coding%20agents&descSize=20&descAlignY=62&descAlign=50" alt="ctxr-dev" />
</a>

<br />

<a href="https://github.com/ctxr-dev">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&pause=1200&color=8B5CF6&center=true&vCenter=true&multiline=false&width=720&height=46&lines=Claude+Code+%E2%80%A2+Codex+%E2%80%A2+Cursor+%E2%80%A2+any+MCP+client;Install+only+what+you+need.;Skills.+Agents.+Memory.+Methodology." alt="tagline" />
</a>

<br /><br />

<a href="https://github.com/ctxr-dev"><img src="https://img.shields.io/badge/GitHub-ctxr--dev-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub org" /></a>
<a href="https://www.npmjs.com/org/ctxr"><img src="https://img.shields.io/badge/npm-%40ctxr-CB3837?style=for-the-badge&logo=npm&logoColor=white" alt="npm org" /></a>
<a href="https://github.com/ctxr-dev/start/blob/main/README.md"><img src="https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge" alt="MIT" /></a>
<a href="https://modelcontextprotocol.io"><img src="https://img.shields.io/badge/MCP-native-3776AB?style=for-the-badge" alt="MCP native" /></a>

<br />

<a href="https://docs.claude.com/en/docs/agentic-coding/claude-code"><img src="https://img.shields.io/badge/Claude%20Code-compatible-D97757?style=flat-square" alt="Claude Code" /></a>
<a href="https://github.com/openai/codex"><img src="https://img.shields.io/badge/Codex-compatible-10A37F?style=flat-square&logo=openai&logoColor=white" alt="Codex" /></a>
<a href="https://cursor.com"><img src="https://img.shields.io/badge/Cursor-compatible-000000?style=flat-square" alt="Cursor" /></a>
<a href="https://github.com/ctxr-dev"><img src="https://img.shields.io/badge/Any%20MCP%20client-yes-6366F1?style=flat-square" alt="Any MCP client" /></a>

</div>

<br />

<div align="center">
  <sub><b>Pick a memory. Add the skills you want. Drop in agents when you need more horsepower.</b></sub>
</div>

---

## ⚡ 60-second start

```bash
# 1. Run the installer (no global install)
npx @ctxr/kit

# 2. Pick a memory backend (one prompt, one decision)
#    Wiki  → https://github.com/ctxr-dev/llm-wiki-memory#install
#    RAG   → https://github.com/ctxr-dev/memory#install

# 3. Add the skill almost everyone wants
npx @ctxr/kit install @ctxr/skill-code-review
```

That is the whole start. Everything below is opt-in.

---

## 🧠 Pick your memory

Self-improving memory: your agent recalls past lessons before it works and saves a new one the moment
you correct it, so the same mistake does not recur. Both options expose the same tools and behavior, so
you can switch later. Install one, not both.

<table>
  <thead>
    <tr>
      <th></th>
      <th align="center">📒 Wiki <sub>(default)</sub></th>
      <th align="center">🧬 RAG</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Repo</b></td>
      <td align="center">
        <a href="https://github.com/ctxr-dev/llm-wiki-memory"><img src="https://img.shields.io/badge/ctxr--dev-llm--wiki--memory-22c55e?style=flat-square&logo=github" alt="llm-wiki-memory" /></a><br/>
        <a href="https://github.com/ctxr-dev/llm-wiki-memory"><img src="https://img.shields.io/github/stars/ctxr-dev/llm-wiki-memory?style=flat-square&label=%E2%98%85" alt="stars" /></a>
      </td>
      <td align="center">
        <a href="https://github.com/ctxr-dev/memory"><img src="https://img.shields.io/badge/ctxr--dev-memory-8B5CF6?style=flat-square&logo=github" alt="memory" /></a><br/>
        <a href="https://github.com/ctxr-dev/memory"><img src="https://img.shields.io/github/stars/ctxr-dev/memory?style=flat-square&label=%E2%98%85" alt="stars" /></a>
      </td>
    </tr>
    <tr>
      <td><b>Stores as</b></td>
      <td>git-versioned markdown in your repo</td>
      <td>local Dify vector store</td>
    </tr>
    <tr>
      <td><b>Infra</b></td>
      <td>none (Node + git)</td>
      <td>Docker + Dify</td>
    </tr>
    <tr>
      <td><b>Best for</b></td>
      <td>solo, small, and medium projects; offline; low overhead</td>
      <td>large corpora; teams; retrieval precision at scale</td>
    </tr>
    <tr>
      <td><b>One-prompt AI install</b></td>
      <td><a href="https://github.com/ctxr-dev/llm-wiki-memory#install">llm-wiki-memory#install</a></td>
      <td><a href="https://github.com/ctxr-dev/memory#install">memory#install</a></td>
    </tr>
  </tbody>
</table>

> **Default to Wiki.** Choose RAG when the corpus is large, several people or agents share one store, or
> Docker is already in your stack. Not ready for persistent memory? Skip it. Nothing else depends on it.

---

## 🗺️ How the pieces fit

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#1e1b4b','primaryTextColor':'#fafafa','primaryBorderColor':'#8B5CF6','lineColor':'#a78bfa','fontFamily':'JetBrains Mono'}}}%%
flowchart TB
    user(["👩‍💻 You"])
    agent{{"🤖 Your agent\n Claude Code · Codex · Cursor · any MCP client"}}

    subgraph installer ["📦 Installer"]
      kit["@ctxr/kit"]
    end

    subgraph skills ["🛠️ Skills"]
      sCR["skill-code-review"]
      sFE["skill-frontend-excellence"]
      sLW["skill-llm-wiki"]
    end

    subgraph agents ["🧑‍🚀 Agents"]
      aSE["agent-staff-engineer"]
      aCE["agent-codebase-explorer"]
      aPR["agent-plan-reviewer"]
      aIA["agent-implementation-auditor"]
    end

    subgraph memory ["🧠 Memory"]
      mW["llm-wiki-memory"]
      mR["memory (RAG)"]
    end

    subgraph integ ["🔌 Integrations"]
      mcp["@ctxr/mcp-github"]
      meth["github-dev-methodology"]
    end

    user --> agent
    agent --> kit
    kit -.installs.-> skills
    kit -.installs.-> agents
    agent --> memory
    agent --> integ
    aSE -.uses.-> sLW
    aSE -.reviews via.-> sCR
```

---

## 📦 Installer

| Package | Use it to | Badges |
| --- | --- | --- |
| [`@ctxr/kit`](https://github.com/ctxr-dev/kit) | install, update, and scaffold skills and agents (`npx @ctxr/kit`, no global) | [![npm](https://img.shields.io/npm/v/@ctxr/kit?style=flat-square&logo=npm&label=npm)](https://www.npmjs.com/package/@ctxr/kit) [![stars](https://img.shields.io/github/stars/ctxr-dev/kit?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/kit) |

---

## 🛠️ Skills

> Install any skill with `npx @ctxr/kit install @ctxr/<name>`.

| Skill | Use it to | Badges |
| --- | --- | --- |
| [`@ctxr/skill-code-review`](https://github.com/ctxr-dev/skill-code-review) | multi-specialist review with a GO / NO-GO verdict | [![npm](https://img.shields.io/npm/v/@ctxr/skill-code-review?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/skill-code-review) [![stars](https://img.shields.io/github/stars/ctxr-dev/skill-code-review?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/skill-code-review) |
| [`@ctxr/skill-frontend-excellence`](https://github.com/ctxr-dev/skill-frontend-excellence) | ship fast, accessible, distinctive web UI (Lighthouse 95+ mobile, 99+ desktop) | [![npm](https://img.shields.io/npm/v/@ctxr/skill-frontend-excellence?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/skill-frontend-excellence) [![stars](https://img.shields.io/github/stars/ctxr-dev/skill-frontend-excellence?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/skill-frontend-excellence) |
| [`@ctxr/skill-llm-wiki`](https://github.com/ctxr-dev/skill-llm-wiki) | make your agent read docs and code token-efficiently | [![npm](https://img.shields.io/npm/v/@ctxr/skill-llm-wiki?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/skill-llm-wiki) [![stars](https://img.shields.io/github/stars/ctxr-dev/skill-llm-wiki?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/skill-llm-wiki) |

---

## 🧑‍🚀 Agents

> Install with `npx @ctxr/kit install @ctxr/<name>`.

| Agent | Use it to | Badges |
| --- | --- | --- |
| [`@ctxr/agent-staff-engineer`](https://github.com/ctxr-dev/agent-staff-engineer) | drive a ticket to an open PR, then hand off before merge (pulls in `skill-llm-wiki`, reviews via `skill-code-review`) | [![npm](https://img.shields.io/npm/v/@ctxr/agent-staff-engineer?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/agent-staff-engineer) [![stars](https://img.shields.io/github/stars/ctxr-dev/agent-staff-engineer?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/agent-staff-engineer) |
| [`@ctxr/agent-codebase-explorer`](https://github.com/ctxr-dev/agent-codebase-explorer) 🆕 | read-only "where is X / what references Y" search subagent, capped structured reports | [![npm](https://img.shields.io/npm/v/@ctxr/agent-codebase-explorer?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/agent-codebase-explorer) [![stars](https://img.shields.io/github/stars/ctxr-dev/agent-codebase-explorer?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/agent-codebase-explorer) |
| [`@ctxr/agent-plan-reviewer`](https://github.com/ctxr-dev/agent-plan-reviewer) 🆕 | adversarially review a plan or design *before* you confirm it: gaps, blind spots, edge cases, infeasibilities | [![npm](https://img.shields.io/npm/v/@ctxr/agent-plan-reviewer?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/agent-plan-reviewer) [![stars](https://img.shields.io/github/stars/ctxr-dev/agent-plan-reviewer?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/agent-plan-reviewer) |
| [`@ctxr/agent-implementation-auditor`](https://github.com/ctxr-dev/agent-implementation-auditor) 🆕 | post-build conformance audit: missed plan items, divergences, cross-implementation parity | [![npm](https://img.shields.io/npm/v/@ctxr/agent-implementation-auditor?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/agent-implementation-auditor) [![stars](https://img.shields.io/github/stars/ctxr-dev/agent-implementation-auditor?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/agent-implementation-auditor) |

> 💡 The three 🆕 agents are **read-only by design**: their tool surface is scoped to `Read / Grep / Glob / Bash`, so a flaky MCP connector cannot kill subagent init. Drop them in front of the staff-engineer loop or use them standalone.

---

## 🔌 MCP servers

| Server | Use it to | Setup | Badges |
| --- | --- | --- | --- |
| [`@ctxr/mcp-github`](https://github.com/ctxr-dev/mcp-github) | structured GitHub tool calls instead of `gh` shell-outs | [register it](https://github.com/ctxr-dev/mcp-github#use-as-an-mcp-server) | [![npm](https://img.shields.io/npm/v/@ctxr/mcp-github?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/mcp-github) [![stars](https://img.shields.io/github/stars/ctxr-dev/mcp-github?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/mcp-github) |

---

## 📐 Methodology

| Repo | Use it to | How | Badges |
| --- | --- | --- | --- |
| [`ctxr-dev/github-dev-methodology`](https://github.com/ctxr-dev/github-dev-methodology) | a consistent GitHub issue and PR workflow, plus subagent orchestration | clone into your project; [read it](https://github.com/ctxr-dev/github-dev-methodology) | [![stars](https://img.shields.io/github/stars/ctxr-dev/github-dev-methodology?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/github-dev-methodology) |

---

## 📚 Libraries

| Package | Use it to | Badges |
| --- | --- | --- |
| [`@ctxr/fsm`](https://github.com/ctxr-dev/fsm) | author your own deterministic multi-agent workflow (usually transitive, via a skill or agent) | [![npm](https://img.shields.io/npm/v/@ctxr/fsm?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/fsm) [![stars](https://img.shields.io/github/stars/ctxr-dev/fsm?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/fsm) |

---

## 🌐 Recommended external plugins

The ctxr stack plays nicely with other open skill and agent collections. A few we like:

| Source | Install | What you get |
| --- | --- | --- |
| [`mattpocock/skills`](https://github.com/mattpocock/skills) | `npx skills@latest add mattpocock/skills` | Matt Pocock's TypeScript and authoring skills, batteries included |
| [`anthropics/skills`](https://github.com/anthropics/skills) | `npx skills@latest add anthropics/skills` | Anthropic's reference skills (PDFs, spreadsheets, Office, web-design) |
| [`wshobson/agents`](https://github.com/wshobson/agents) | clone and point your agent loader at it | Community catalog of Claude Code subagents |

> The `npx skills@latest add <owner>/<repo>` pattern works for any GitHub repo that follows the
> [skills](https://github.com/anthropics/skills) layout. Use `@ctxr/kit` for ctxr packages, `skills` CLI
> for everything else, side by side.

---

## 🎯 Starter stacks

<table>
  <thead>
    <tr><th>Stack</th><th>What you install</th><th>Why</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><b>🧍 Solo / side project</b></td>
      <td><code>kit</code> + Wiki memory + <code>skill-code-review</code><br/><sub>add <code>skill-frontend-excellence</code> if you ship web UI</sub></td>
      <td>zero infra, every commit reviewed, lessons accumulate</td>
    </tr>
    <tr>
      <td><b>👥 Small team on GitHub</b></td>
      <td>above + <code>github-dev-methodology</code> (<code>pr-only</code> preset) + <code>mcp-github</code></td>
      <td>shared PR loop without imposing the whole methodology at once</td>
    </tr>
    <tr>
      <td><b>🏢 Larger team</b></td>
      <td>RAG memory + <code>skill-code-review</code> + <code>agent-staff-engineer</code> + <code>agent-plan-reviewer</code> + <code>agent-implementation-auditor</code> + methodology (<code>full</code> preset) + <code>mcp-github</code></td>
      <td>plan is adversarially reviewed, build is automated, output is audited against plan</td>
    </tr>
  </tbody>
</table>

---

## 🤝 Contribute

All repos are MIT licensed and developed in the open at **[github.com/ctxr-dev](https://github.com/ctxr-dev)**.

- 🐞 Found a bug? Open an issue on the relevant repo.
- 💡 Have an idea? Discussions are on, fire away.
- 🛠️ Want to ship a skill or agent under `@ctxr/`? Start from [`@ctxr/kit`](https://github.com/ctxr-dev/kit) and PR it.

<div align="center">
  <br/>
  <sub>Built with ❤️ for agents that ship.</sub>
  <br/><br/>
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=20,8,2,12,30&height=120&section=footer" alt="footer" />
</div>
