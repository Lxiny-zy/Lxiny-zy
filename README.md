# LI Xinyu

Independent developer working on **AI agent systems and LLM infrastructure**.

Mostly interested in what makes an agent *reliable* rather than merely demo-able —
orchestration, observability, evidence verification, and knowing where deterministic
code should replace model judgment.

`Python` · `Go` · `TypeScript`

---

## Projects

### [deep-research-agent](https://github.com/Lxiny-zy/deep-research-agent)
`Python` · `FastAPI` · `React` · `Docker`

A multi-agent research system: decompose a question → retrieve in parallel →
reflect on gaps → synthesize a cited report. Built around the parts that usually get skipped.

- **Workflow-as-data** — versioned graphs (nodes, edges, conditions, join modes) stored in the DB and executed from it, not hardcoded
- **Evidence gating** — every finding must carry a verbatim source quote; only claims that verify *and* hold up semantically reach the report
- **Injection defense** — retrieved content is screened before it reaches the model; isolate/reject decisions become structured audit events
- **Cross-source corroboration** — registrable-domain checks so subdomains and punycode aliases of one publisher don't count twice
- **Deterministic metrics** — verification rate, report admission rate, independent-publisher count; version regression without a judge model

### [claude-evo-skill](https://github.com/Lxiny-zy/claude-evo-skill)
`Shell`

`/evo` — a self-evolution skill for Claude Code. Long sessions accumulate context pollution:
`/compact` clears everything, `/rewind` restores code but not understanding, and lessons from
failed attempts are lost. `/evo` pins a clean baseline, then returns with that baseline *plus*
what was learned from the failures.

---

## Upstream contributions

Fixes and features sent to projects I actually use:

- **[looplj/axonhub](https://github.com/looplj/axonhub)** — per-channel API key rule actions *(merged)*, plus failover rules and an OpenAI message-content fix for strict upstreams
- **[esengine/DeepSeek-Reasonix](https://github.com/esengine/DeepSeek-Reasonix)** — `-c` shorthand resolution for `--continue` *(merged)*, plus corrupt-metadata cleanup on startup and missing-reasoning warning heuristics

---

## Currently exploring

How to make multi-agent systems auditable and reproducible — capturing what the model
actually saw at decision time, and drawing the line between what a model should decide
and what code should enforce.
