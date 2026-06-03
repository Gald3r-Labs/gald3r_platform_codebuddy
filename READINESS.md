# gald3r Readiness Report — CodeBuddy Code

> An honest accounting of how much of the gald3r framework installs natively on this
> platform, what degrades to an approximation, and what has no native home yet.
> Generated from a live documentation crawl on 2026-06-02.

**Overall readiness: ✅ Full.** CodeBuddy Code (Tencent Cloud) is a CLI/agent closely
modeled on Claude Code. Every gald3r-relevant layer — commands, rules, agents, skills, and
hooks — lands on a native mechanism, with full MCP support alongside. gald3r's Claude-Code
primitives port over with minimal adaptation.

## C.R.A.S.H. capability grid

| | Capability | Native? | What gald3r gets here | The gap |
|---|---|:---:|---|---|
| **C** | Commands | ✅ | Custom slash commands as `.codebuddy/commands/*.md` (project + global); YAML frontmatter, `$ARGUMENTS`, `!`shell`, `@file`, colon-namespacing | None — gald3r's `@g-*` set installs as native slash commands |
| **R** | Rules | ✅ | `CODEBUDDY.md` (AGENTS.md fallback) + modular `.codebuddy/rules/*.md`, project & user scope, `@import` includes, auto-loaded at startup | None — gald3r rules load as first-class memory/rules files |
| **A** | Agents | ✅ | Markdown sub-agents in `.codebuddy/agents/`; own context window, custom prompt, per-agent tools/model/skills, background execution | None — gald3r's `g-agnt-*` roles map directly to native sub-agents |
| **S** | Skills | ✅ | Agent-Skills `SKILL.md` at `.codebuddy/skills/<name>/`; model-invoked, `allowed-tools`, inline hooks, isolated `fork` context (v2.0+) | None — gald3r skills install as native `SKILL.md` packages |
| **H** | Hooks | ✅ | 27+ lifecycle events in `.codebuddy/settings.json`; shell scripts via stdin JSON — SessionStart, PreToolUse, Stop, FileChanged, and more | Windows forces hooks under Git Bash — gald3r's `g-hk-*` wiring fires natively otherwise |

_Legend: ✅ native · ⚠️ partial / approximated · ❌ no native mechanism · ❓ unverified_

**Beyond C.R.A.S.H. — MCP: ✅** Full native MCP via `.mcp.json` (user/project/local scope)
and `codebuddy mcp add` — STDIO, SSE, and HTTP transports, JSONC supported. Sub-agents and
skills can reach gald3r's MCP backend directly.

## Adoptable extras (non-C.R.A.S.H.)

Platform-native strengths gald3r can lean on, and which need wiring:

| Feature | Status | gald3r fit |
|---|:---:|---|
| Plugin system (bundles Skills / Agents / Hooks / MCP / LSP) | ✅ present | Natural package format for shipping a full gald3r bundle |
| Output styles / output formats | ⚙️ needs customization | Could carry gald3r's report-rendering presets |
| Context references (`@workspace`, `#Codebase`, `@file`) | ✅ present | Extra context surfaces; no gald3r work required |
| ACP compatibility + open SDK + plan mode + sandboxed execution | ✅ present | Automation entry points for gald3r tooling and safe task runs |
| LSP servers (bundled via plugins) | ➖ n.a. | Editor tooling; outside gald3r's primitive set |

## The ceiling, and what's beyond it

gald3r runs at full strength on this platform — commands, rules, agents, skills, and hooks all map onto native mechanisms, so the framework installs without compromise. As third-party adaptation goes, this is the high end: nothing here has to be approximated.

But adaptation, however clean, is still gald3r living as a guest inside someone else's tool. The native build goes further — **gald3r_agent**, running on the **gald3r throne** over the **gald3r_world_tree** — where these primitives aren't mapped onto a host, they *are* the substrate. Same framework, no host in between.

> ### gald3r_agent — coming soon. 🌳

---

<sub>Capabilities verified against the platform's official documentation on 2026-06-02, and
re-verified each release via the gald3r platform-docs crawl. This report describes gald3r's
third-party adaptation surface; it is not an endorsement or critique of the platform itself.</sub>
