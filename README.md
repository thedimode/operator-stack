# operator-stack
**The reference implementation for Personal AI Architecture.**
**Maintainer:** Timothy Shin · [thedimode.com](https://thedimode.com)
**License:** MIT

---

This repository is the reference implementation of [Personal AI Architecture](https://github.com/thedimode/personal-ai-architecture). It contains the prompts, templates, schemas, and hook code an AI Operator needs to build their own stack from scratch.

- **For the discipline's specification**, see [`thedimode/personal-ai-architecture`](https://github.com/thedimode/personal-ai-architecture).
- **For the workbook that teaches the discipline**, see [thedimode.com/workbook](https://thedimode.com/workbook).
- **For the maintainer's own running stack as a proof artifact**, see [`thedimode/thedimode`](https://github.com/thedimode/thedimode).

## What's inside

```
operator-stack/
├── README.md                       (this file)
├── LICENSE                         (MIT)
├── CHANGELOG.md
│
├── prompts/                        Nine prompts, each as a standalone .md
│   ├── 01-quick-profile-interview.md
│   ├── 02-identity-loader.md
│   ├── 03-voice-extraction-starter.md
│   ├── 04-persona-synthesizer.md
│   ├── 05-decisions-log-initializer.md
│   ├── 06-current-state-template.md
│   ├── 07-end-of-session-reflection.md
│   ├── 08-morning-brief-generator.md
│   └── 09-weekly-rollup-generator.md
│
├── templates/                      Empty file templates with frontmatter
│   ├── profile.md.tmpl
│   ├── persona_profile.md.tmpl
│   ├── decisions.md.tmpl
│   ├── current_state.md.tmpl
│   └── session_log.md.tmpl
│
├── skills/                         Example skills following the schema
│   ├── README.md
│   ├── korean-document-quality/   (worked example)
│   ├── decision-frame/            (worked example)
│   └── memo-drafting/             (worked example)
│
├── hooks/                          Working hook code, MIT-licensed
│   ├── README.md
│   ├── session-briefing/          (loads identity at session start)
│   ├── recall/                    (front-door vault retrieval)
│   ├── fact-extractor/            (append-only fact capture)
│   └── auto-doctor/               (deterministic state-drift checks)
│
├── schemas/                        Spec schemas as JSON Schema + examples
│   ├── profile.schema.json
│   ├── decisions.schema.json
│   ├── current-state.schema.json
│   ├── session-log.schema.json
│   └── skill.schema.json
│
└── tests/                          Compliance test list
    └── compliance.md
```

## Dependencies on prior art

This implementation builds on, and stands alongside, work by several practitioners:

- **Andrej Karpathy** — *Software 2.0* (2017) framed code-as-prompt as a real category. The prompts in this repo are not casual templates; they are versioned, named, output-typed artifacts.
- **Geoffrey Litt** — local-first personal software, malleable software, "Stevens." The instinct that personal tools should be owned and editable by the user runs through every file in this repo.
- **Simon Willison** — public agentic-engineering patterns, the LLM CLI tool, the model of practitioner-publisher who ships what they actually use.
- **Khoj, Letta, mem0** — open and commercial memory-layer implementations. This toolkit is format-only and worker-facing; those projects are framework-and-product. We are complementary, not competing.

Personal AI Architecture as a discipline is younger than these. The reference implementation in this repo is one way to instantiate it; other reference implementations are welcome.

## Quick start

If you've never built one of these before:

```bash
git clone https://github.com/thedimode/operator-stack
cd operator-stack

# 1. Copy a template into your AI working directory
cp templates/profile.md.tmpl ~/Documents/MyAI/profile.md

# 2. Open prompts/01-quick-profile-interview.md in your AI of choice
#    (Claude, ChatGPT, Gemini — any will do)

# 3. Paste the prompt. Answer the nine questions. Save the output
#    as profile.md.

# 4. Continue through prompts 02-09 over the following weeks.
```

Then read the workbook for the narrative. The toolkit is the code; the workbook is the build.

## How this differs from a prompt library

| Standard prompt library | This toolkit |
|---|---|
| Flat collection of prompts | Nine prompts in a defined sequence with named outputs |
| Outputs are throwaway text | Outputs are durable markdown files on disk |
| Prompts evolve invisibly | Versioned, semver-tagged, changelog-tracked |
| One-shot usage | Compounding, dependency-graphed, multi-week |
| Vendor-coupled | Vendor-agnostic by design |
| Closed-format outputs | Open-format outputs (JSON Schema for every file type) |

If a prompt library is a recipe book, this is a kitchen.

## Contributing

Issues and PRs welcome. We accept:

- Bug fixes to existing prompts (clarity, instruction following, output schema)
- New worked-example skills (must follow `schemas/skill.schema.json`)
- New worked-example hooks (must be vendor-agnostic and self-contained)
- Translations of prompts into additional languages (Korean, Japanese, Mandarin, Spanish currently in scope)

We do not accept:

- Vendor-coupled implementations (no "ChatGPT only" or "Claude only" prompts)
- Untested code in `hooks/`
- Skills without a worked example
- Cosmetic-only PRs

## Versioning

Semver. Pin to a tag. Pre-1.0 is draft; expect schema-breaking changes between minor versions until v1.0.0.

## Status

**v0.9 (Draft).** Open for forking and citation. Issues welcome. v1.0 ships when schemas reach RC and the workbook ships v2.

---

*If you build with this, tell us. We're keeping a public list of compliant implementations at the maintainer's discretion.*
