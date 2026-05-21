# Prompt 02 · Identity Loader

**Output:** Active session context primed with the operator's identity
**Time to complete:** ~30 seconds per session
**Runtime:** Any LLM
**Spec section:** [01 · Identity files](https://github.com/thedimode/personal-ai-architecture/tree/main/sections/01-identity-files)

## Purpose

Load `profile.md` (and optionally `persona_profile.md`) into the active AI session before any real work begins. This is the operational counterpart to Prompt 01: Prompt 01 produces the identity file; Prompt 02 ensures the AI actually uses it.

The single most common failure mode of Personal AI Architecture is having a well-built `profile.md` that the AI never reads because the operator forgets to load it. This prompt closes that gap.

## How to use

Three ways, in increasing order of automation:

### Manual (works everywhere)

At the start of each AI session, paste the prompt below, replacing `<PROFILE_CONTENT>` with the actual content of your `profile.md`.

### Semi-automated (Claude Projects, ChatGPT Custom GPTs)

Save `profile.md` as a project knowledge file. Configure the project's system prompt to be the prompt below, minus the `<PROFILE_CONTENT>` paste (the project's RAG layer surfaces the file automatically).

### Fully automated (Claude Code, terminal-based runtimes, MCP)

Configure a session-start hook to read `profile.md` from disk and inject it as the first message of every session. The reference hook ships in `hooks/session-briefing/` in v0.10.

## The prompt

```
Before I give you any task, read the following profile carefully. Do
not commentate on it. Do not summarize it back to me. This profile is
the canonical record of who I am and how I want you to work with me.
Treat it as standing instruction for this entire session.

For any conflict between this profile and your default behavior, the
profile wins. For any conflict between this profile and a specific
instruction I give later in this session, the later instruction wins
for that one task but the profile resumes after.

When you have read and understood the profile, respond with the
single sentence: "Profile loaded. What are we working on?"

Do not say more than that. Do not list what you learned. Do not paraphrase.

Profile follows.

---

<PROFILE_CONTENT>

---

End of profile. Respond only with the loading-confirmation sentence
specified above.
```

## What this prompt is doing

Three things at once:

1. **Naming the profile as canonical.** Without this framing, the AI may treat the profile as informational background rather than as standing instruction. The "canonical record" + "standing instruction" framing shifts the AI from descriptive mode to operational mode.

2. **Establishing conflict resolution.** The profile-vs-default and profile-vs-later-instruction rules pre-empt the most common ambiguity: what happens when the AI's defaults contradict the profile, and what happens when a specific task asks for something the profile disallows. The rules are: profile beats default; later instruction wins for that one task; profile resumes after.

3. **Suppressing the AI's instinct to performatively acknowledge.** Most models, given a long context block, will respond with a summary of what they read. That summary is wasted output. The "Profile loaded. What are we working on?" forcing function eliminates it.

## After loading

The AI is now primed to do the actual work of the session with the operator's identity active. The remaining prompts in the Operator Stack (Prompts 03-09) assume identity-loaded sessions. Without Prompt 02, they may produce thin or off-voice output.

## Compatibility

Tested against Claude, ChatGPT, and Gemini. Models occasionally violate the "respond only with the loading-confirmation sentence" rule by adding a sentence of acknowledgment. This is harmless. Some models will resist the forcing function and produce a paragraph; if yours does, you can tighten the prompt with "Respond ONLY with the exact sentence: 'Profile loaded. What are we working on?' Any additional output violates this instruction."

## License

MIT.
