# operator-stack

**Status:** v0.9 (Draft) · See [ROADMAP.md](./ROADMAP.md) and [CHANGELOG.md](./CHANGELOG.md)
**Maintainer:** Timothy Shin · [thedimode.com](https://thedimode.com)
**License:** [MIT](./LICENSE)

The reference implementation for [Personal AI Architecture](https://github.com/thedimode/personal-ai-architecture): nine prompts, file templates, skill schema, and hook examples for building your own portable AI operating system.

## The Personal AI Architecture project

- [thedimode/personal-ai-architecture](https://github.com/thedimode/personal-ai-architecture) — the specification
- **thedimode/operator-stack** — reference implementation (this repo)
- [thedimode/thedimode](https://github.com/thedimode/thedimode) — the maintainer's personal proof artifact
- [thedimode.com/handbook](https://thedimode.com/handbook) — the handbook that teaches the discipline

## What this repository will contain

This repository is in active development. v0.9 is currently a placeholder; v0.10 ships the first end-to-end vertical slice (one prompt → one output file → one skill → one hook). See [ROADMAP.md](./ROADMAP.md) for the shipping schedule.

When complete, this repository will provide:

- Nine copy-paste prompts with named outputs, vendor-agnostic
- File templates conforming to the spec's schemas
- Worked-example skills demonstrating the description-triggered loading pattern
- Working hook examples covering session start, retrieval, fact capture, and drift detection
- JSON Schema files for every spec-defined artifact
- A compliance test list

## How this differs from a prompt library

| Standard prompt library | This toolkit (when complete) |
|---|---|
| Flat collection of prompts | Nine prompts in a defined sequence with named outputs |
| Outputs are throwaway text | Outputs are durable markdown files on disk |
| Prompts evolve invisibly | Versioned, semver-tagged, changelog-tracked |
| One-shot usage | Compounding, dependency-graphed, multi-week |
| Vendor-coupled | Vendor-agnostic by design |
| Closed-format outputs | Open-format outputs (JSON Schema for every file type) |

If a prompt library is a recipe book, this is a kitchen.

## Acknowledgments and prior art

This implementation builds on, and stands in conversation with:

- **Simon Willison** — the [LLM CLI tool](https://github.com/simonw/llm) and the model of practitioner-publisher who ships what they actually use. The "one runnable example in under five minutes" standard this toolkit aspires to is Willison's standard.
- **Geoffrey Litt** — local-first personal software, malleable software, "Stevens." The instinct that personal tools should be owned and editable by the user runs through every file in this repo.
- **Gordon Brander** ([Subconscious](https://subconscious.network)) — self-sovereign personal computing in the AI era.
- **Andrej Karpathy** — public, reproducible, minimal reference implementations ([nanoGPT](https://github.com/karpathy/nanoGPT)). The "smallest readable version of the thing" standard.
- **Khoj, Letta, Mem0** — open and commercial memory-layer implementations. This toolkit is complementary: format-only and worker-facing.

## Contributing

Issues and pull requests welcome. See [CONTRIBUTING.md](./CONTRIBUTING.md) and [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md). For security disclosures, see [SECURITY.md](./SECURITY.md).

When v0.10 ships, accepted contributions include:

- Bug fixes to existing prompts (clarity, instruction following, output schema conformance)
- New worked-example skills (must follow the spec's skill schema)
- New worked-example hooks (must be vendor-agnostic and self-contained)
- Translations of prompts (Korean, Japanese, Mandarin, Spanish in scope)

Not accepted:

- Vendor-coupled implementations
- Untested hook code
- Skills without a worked example
- Cosmetic-only PRs

## Versioning

Semantic versioning. Pin to a tag. Pre-1.0 is draft; expect schema-breaking changes between minor versions until v1.0.0.

## Status

**v0.9 (Draft).** Repository scaffolding only. v0.10 ships the first vertical slice.

---

Maintained by Timothy Shin.
