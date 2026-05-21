# Security Policy

## Reporting a vulnerability

If you discover a security-relevant issue in the operator-stack reference implementation (for example, a hook that exposes credentials, a prompt that exfiltrates data, or a skill that violates a documented trust boundary), please report it privately. Do not file a public GitHub issue.

Email: **timothyshin2025@gmail.com**

You can expect an initial response within seven days. If a coordinated disclosure is appropriate, we will work with you on a timeline.

## Threat model

The operator-stack runs in the user's own AI client (Claude, ChatGPT, Cursor, terminal, etc.) and reads and writes files in the user's filesystem. The maintainer does not control the runtime, the LLM provider, or the user's environment. Security responsibilities are split:

- **This project is responsible for:** the prompts not exfiltrating user data; the hooks not executing arbitrary code from untrusted input; the skills not bypassing documented autonomy-ladder constraints; the templates not leaking secrets.
- **The user is responsible for:** their LLM provider's security; their filesystem permissions; their secrets management; their decision about which skills and hooks to trust.

## Supported versions

| Version | Supported |
|---|---|
| v0.9 (Draft) | Yes |

Pre-1.0 versions receive security responses on a best-effort basis.
