# Contributing to operator-stack

Thanks for your interest in contributing to the operator-stack reference implementation. This document explains how to file issues, propose changes, and submit pull requests.

This implementation is published under [MIT](./LICENSE). By contributing you agree your contributions are licensed under the same terms.

## Before you contribute

- Read the [README](./README.md) and the current [ROADMAP](./ROADMAP.md).
- This repository is the reference implementation of the [Personal AI Architecture specification](https://github.com/thedimode/personal-ai-architecture). Changes to file formats, schemas, or protocols belong in the spec repo, not here. Changes to prompts, templates, skills, and hooks belong here.
- Check open and closed [issues](https://github.com/thedimode/operator-stack/issues).
- Review the [Code of Conduct](./CODE_OF_CONDUCT.md).

## Three kinds of contribution

### 1. Prompts, templates, skills, hooks

The core artifacts of the reference implementation.

- File an issue first if the change is substantive (new prompt, new skill, new hook).
- Bug fixes to existing artifacts can be filed as PRs directly.
- All contributions must be vendor-agnostic. Prompts that only work with one LLM are out of scope.
- Skills must follow the spec's `skills` schema (`./schemas/skill.schema.json` once shipped).
- Hooks must be self-contained, tested, and not depend on a specific runtime.

### 2. Documentation

Improvements to the README, ROADMAP, CHANGELOG, or any explanatory text.

- Can be filed as PRs directly.

### 3. Translations

Translations of prompts and templates into Korean, Japanese, Mandarin, Spanish, or other languages. Welcome at v1.0+.

## AI-assisted contributions

If you used an AI tool to draft any part of your contribution, disclose it in the PR description. A line like *"This PR was drafted with Claude / ChatGPT / Cursor and reviewed by me"* is sufficient. The disclosure is a transparency norm.

## Pull request expectations

- Branch from `main`.
- One logical change per PR.
- Update [CHANGELOG.md](./CHANGELOG.md) under `[Unreleased]`.
- For new skills or hooks, include a worked example demonstrating the contribution running end to end.
- Pass any CI checks (added as the toolkit matures).

## What is not accepted

- Vendor-coupled implementations (anything that only works with one LLM provider).
- Untested hook code.
- Skills without a worked example.
- Cosmetic-only PRs (whitespace, comment-only, etc.).

## Maintainer and governance

The maintainer is the sole author at v0.9. Contributor governance opens at v1.0.

For security-relevant issues, see [SECURITY.md](./SECURITY.md) and do not file a public issue.

---

*This CONTRIBUTING.md is modeled on the contribution patterns used by the [Model Context Protocol specification](https://github.com/modelcontextprotocol/specification) and adjacent open-source reference implementations.*
