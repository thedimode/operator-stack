# Prompt 01 · Quick Profile Interview

**Output file:** `profile.md`
**Time to complete:** ~15 minutes
**Runtime:** Any LLM (Claude, ChatGPT, Gemini, Llama, Mistral, Qwen — vendor-agnostic by design)
**Spec section:** [01 · Identity files](https://github.com/thedimode/personal-ai-architecture/tree/main/sections/01-identity-files)

## Purpose

Produce a compliant `profile.md` file (per the [profile.v1 schema](https://github.com/thedimode/personal-ai-architecture/blob/main/sections/01-identity-files/profile-schema.md)) that the operator's AI loads at the start of every session. The output is the foundation of the Operator Stack; everything else in this toolkit assumes `profile.md` exists.

## How to use

1. Open the prompt below in your AI of choice.
2. Paste the prompt.
3. Answer each question as it arrives. Do not skip ahead.
4. After the ninth answer, the AI will produce a synthesized `profile.md` file.
5. Copy the output to `identity/profile.md` in your working tree.
6. Adjust as needed. The file is yours; the AI's synthesis is a starting point, not the final word.

## The prompt

Copy everything between the triple backticks below into your AI of choice.

```
I want you to interview me for about 15 minutes to capture the essentials
of who I am, in my own voice. At the end of the interview, you will
synthesize my answers into a markdown document I can save as profile.md
and load at the start of every future AI session.

Ground rules:

1. Ask one question at a time. Wait for my answer before asking the
   next.
2. If an answer is vague, follow up briefly — but do not push for the
   full depth I would give in a long interview. This is the quick
   version.
3. After my answer to each question, move on to the next one. Do not
   commentate.
4. Do not editorialize on my answers. Capture them in my words, not
   your interpretation.
5. After the ninth answer, synthesize a complete profile.md following
   the schema described at the bottom of this prompt. Use my voice, not
   yours. Use short sentences. Use no em dashes.

Ask me these nine questions in order:

1. Who are you, in two or three sentences? Include nationality if it
   matters, what you do for work, and your family role if any.

2. What are you working on right now? List the two or three things
   that occupy most of your professional attention.

3. How do you think? What is your cognitive style — what do you read
   fast vs. slow, what do you trust in others, what do you distrust?

4. How do you want AI to work with you? What tone do you want? What
   pushback posture? What kind of delivery do you prefer (bulk-and-
   spot-check vs. step-by-step)?

5. What are you NOT? Name two or three things people sometimes assume
   about you that are wrong. Be specific.

6. What is the single most important constraint on your work right
   now? (Time? Attention? Context-switching? Energy?)

7. What is your core ambition? Where do you want to be in five years,
   in one sentence?

8. What are your standing ground rules for any AI working with you?
   Things you want the AI to remember every single session. Examples:
   default language, sentence length preferences, banned punctuation,
   how to handle uncertainty.

9. Anything you want me to add that the previous eight questions
   missed?

After I answer question 9, produce a profile.md file with this
structure, drawing entirely from my answers:

---
spec: https://github.com/thedimode/personal-ai-architecture/tree/main/sections/01-identity-files
schema: profile.v1
last_updated: <today's date in ISO 8601>
canonical: true
language: <en or ko or whatever I am writing in>
---

# profile.md

## Who I am
[Synthesized from Q1]

## What I am working on right now
[Synthesized from Q2, as a bullet list]

## How I think
[Synthesized from Q3]

## How I want AI to work with me
[Synthesized from Q4]

## What I am not
[Synthesized from Q5, as a bullet list]

## My core constraint
[Synthesized from Q6]

## My core ambition
[Synthesized from Q7]

## Ground rules for any AI working with me
[Synthesized from Q8, as a bullet list]

After producing the file, do not commentate. Do not summarize. Do not
ask if I want changes. Just produce the file. I will edit it myself.
```

## After running the prompt

The AI's output should be a markdown file you can copy verbatim to `identity/profile.md`. Run it through the [Section 01 compliance tests](https://github.com/thedimode/personal-ai-architecture/blob/main/sections/01-identity-files/compliance-tests.md) before using it in production.

The most common edits after first generation:

- Tightening the "Ground rules" section: AIs tend to over-include here. Cut anything that is not actually standing.
- Sharpening the "What I am not" section: AIs tend to soften this. Restore the bluntness.
- Adjusting register: if the AI shifted to its own voice instead of yours, rewrite the affected sections by hand.

## What this prompt is not

This is the *quick* version. It produces a working `profile.md` in 15 minutes. It does not produce a deep voice extraction. For that, use Prompt 03 (Voice Extraction Starter) and Prompt 04 (Persona Synthesizer) once they ship in v0.11.

## Compatibility

This prompt is tested against Claude (Sonnet and Opus), ChatGPT (4o and 5), and Gemini (2.5 Pro and 3). If you find a model where the prompt fails, please file an [issue](https://github.com/thedimode/operator-stack/issues) with the model name, the version, and the failure mode.

## License

MIT. Fork it, modify it, redistribute it. Attribution appreciated but not required.
