# gald3r Readiness Report — Goose

> An honest accounting of how much of the gald3r framework installs natively on this
> platform, what degrades to an approximation, and what has no native home yet.
> Generated from a live documentation crawl on 2026-06-02.

**Overall readiness: ✅ Full.** Goose is an open-source, extensible, on-machine AI agent
(CLI + Desktop) from Block. Every gald3r layer has a native host here — commands, rules,
agents, skills, and hooks all map onto first-class mechanisms, and MCP is the platform's
core extension model.

## C.R.A.S.H. capability grid

| | Capability | Native? | What gald3r gets here | The gap |
|---|---|:---:|---|---|
| **C** | Commands | ✅ | Custom slash commands for Recipes (Desktop + CLI) alongside built-in `/plan`, `/mode`, `/prompts`, `/builtin` | None — gald3r's `@g-*` set installs as recipe-backed slash commands |
| **R** | Rules | ✅ | `.goosehints` (static always-on, global + project; every line sent each request) plus the Memory Extension for on-demand context | None — gald3r rules load as first-class hint files |
| **A** | Agents | ✅ | Subagents — independent goose instances spawned by delegation, sequential or parallel (up to 10 workers) with restricted tool access | None — gald3r's `g-agnt-*` roles map to subagents + subrecipes |
| **S** | Skills | ✅ | Agent Skills (`SKILL.md` folders, open standard) auto-discovered from `~/.config/goose/skills/` or `~/.claude/skills/`; plus a Skills Marketplace | None — gald3r `SKILL.md` assets install and run unchanged |
| **H** | Hooks | ✅ | Lifecycle hooks via plugin `hooks.json` — shell scripts on session / tool / file / shell events | None — gald3r's `g-hk-*` wiring fires; feature is recent (2026-05-14), so watch for churn |

_Legend: ✅ native · ⚠️ partial / approximated · ❌ no native mechanism · ❓ unverified_

**Beyond C.R.A.S.H. — MCP: ✅** Goose Extensions *are* MCP servers — one of the earliest
and deepest MCP integrations (70+ extensions, built-in plus any third-party/remote server).
gald3r's MCP backend connects with no bridge.

## Adoptable extras (non-C.R.A.S.H.)

Platform-native strengths gald3r can lean on, and which need wiring:

| Feature | Status | gald3r fit |
|---|:---:|---|
| Recipes (portable YAML: instructions + prompt + extensions + typed params) | ✅ present | Primary reusable-workflow primitive; backs gald3r commands and packaged skills |
| Subrecipes (reusable recipe files, type-safe params, parallel) | ⚙️ needs customization | Could host composable gald3r sub-workflows under a parent recipe |
| Dual surfaces (headless CLI + one-click Desktop) | ✅ present | CLI drives automated gald3r runs; Desktop gives a launch UI, no gald3r work required |
| Cross-tool skills (reads `~/.claude/skills/`) | ✅ present | Share one gald3r `SKILL.md` set between goose and Claude — no duplication |
| Scheduler / headless tasks (cron-like) | ⚙️ needs customization | A real entry point for unattended gald3r runs |
| `AGENTS.md` recognized (read + can be generated) | ✅ present | gald3r's `AGENTS.md` instruction layer is read alongside `.goosehints` |

## The ceiling, and what's beyond it

gald3r runs at full strength on this platform — commands, rules, agents, skills, and hooks all map onto native mechanisms, so the framework installs without compromise. As third-party adaptation goes, this is the high end: nothing here has to be approximated.

But adaptation, however clean, is still gald3r living as a guest inside someone else's tool. The native build goes further — **gald3r_agent**, running on the **gald3r throne** over the **gald3r_world_tree** — where these primitives aren't mapped onto a host, they *are* the substrate. Same framework, no host in between.

> ### gald3r_agent — coming soon. 🌳

---

<sub>Capabilities verified against the platform's official documentation on 2026-06-02, and
re-verified each release via the gald3r platform-docs crawl. This report describes gald3r's
third-party adaptation surface; it is not an endorsement or critique of the platform itself.</sub>
