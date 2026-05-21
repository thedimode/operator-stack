# operator-stack · Roadmap

**Status as of 2026-05-21:** v0.9 (Draft). README scaffolding only. First vertical slice ships in v0.10.

This roadmap is the source of truth for what is currently in this repository, what is in development, and what is planned. The README does not promise content that does not exist on disk; this file is where the schedule lives.

## What is in this repository today

- `README.md` — orientation, prior-art acknowledgments, license
- `LICENSE` — MIT
- `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `CHANGELOG.md`, `ROADMAP.md` (this file)

## v0.10 target — first vertical slice ships

A single end-to-end runnable example: one prompt that produces one named output file, one skill that reads that file, one hook that updates it. Runnable in under five minutes from `git clone`.

| Artifact | Path | Status |
|---|---|---|
| Quick profile interview prompt | `prompts/01-quick-profile-interview.md` | In progress, target Q3 2026 |
| Identity loader prompt | `prompts/02-identity-loader.md` | Target Q3 2026 |
| Profile template | `templates/profile.md.tmpl` | Target Q3 2026 |
| Worked-example skill | `skills/decision-frame/` | Target Q3 2026 |
| Worked-example hook | `hooks/recall/` | Target Q3 2026 |

## v0.11 → v0.14 targets — remaining prompts and templates

| Prompt | Output file |
|---|---|
| 03 · Voice extraction starter | `persona_profile.md` |
| 04 · Persona synthesizer | `persona_profile.md` (continued) |
| 05 · Decisions log initializer | `decisions.md` |
| 06 · Current state template | `current_state.md` |
| 07 · End-of-session reflection | `session_log.md` |
| 08 · Morning brief generator | (generated daily) |
| 09 · Weekly rollup generator | (generated weekly) |

## v1.0 RC targets

- All nine prompts shipping with worked examples
- All five file templates shipping with JSON Schema validation
- At least three worked-example skills
- At least three worked-example hooks
- Compliance test list covering every spec-defined artifact
- CI running schema validation on every PR

## Versioning

Pre-1.0 may include breaking schema changes between minor versions. Pin to a tag in your own implementation.
