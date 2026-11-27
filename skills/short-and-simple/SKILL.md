---
name: short-and-simple
description: Explains a topic, or re-explains the previous answer, in a short and simple way that is easy to take in. Gives a one-line summary, a few short bullets, a tiny example and an offer to go deeper. Use when handling /short-and-simple, or when someone asks to "explain it simply", "keep it short", "in plain English", "dumb it down", "I don't get it" or "simpler please".
---

# Short and Simple

## Overview

Make an idea easy to understand on the first read. The reader gets the core point fast, in everyday words, and decides for themselves whether they want more.

## When to Use

- The user runs `/short-and-simple`, with or without a topic.
- The user says an answer was too long, too technical or hard to follow.

Not for deep walkthroughs of a codebase. Use `teach` when the person wants to really understand a subsystem, `how` for detailed code behavior and `why` for design rationale.

## Process

### 1. Pick the subject

- **A topic was given** (for example `/short-and-simple what is a webhook`): explain that topic.
- **No topic was given**: re-explain your previous reply. Keep its facts, drop the detail.
- **No topic and no previous reply**: ask in one line what they want explained.

If the topic is about code in this repo, read just enough of it to be correct. Don't run a full investigation.

### 2. Write the answer in this shape

1. **One-line summary.** What it is, or what the answer is, in one plain sentence.
2. **Three to five bullets.** The key points only. One idea per bullet, one short sentence each.
3. **A tiny example.** One small, concrete case: a short code snippet, a command, or a real-life situation. Keep code to a few lines.
4. **Offer to go deeper.** One line at the end, such as "Want me to go deeper on any part?"

Add an analogy only when it makes the idea easier to grasp than the plain explanation does. Skip it when the idea is already clear, and never let it replace the real explanation.

### 3. Keep the words simple

- No jargon. If a technical word can't be avoided, define it in a few plain words the first time it shows up.
- Short sentences. Everyday words.
- Leave out history, edge cases, caveats and alternatives unless they change the answer.
- Keep every fact true. Simpler never means wrong. If something is uncertain, say so in plain words.
- No headers, no preamble ("Great question", "Here's a simple explanation"), no closing summary.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "This topic needs more detail to be accurate." | Give the core idea accurately and offer more. The reader asked for short. |
| "The term is standard, everyone knows it." | The reader asked for simple. Define it or replace it. |
| "An analogy always helps." | A bad or forced analogy adds a second thing to understand. Use one only when it clearly helps. |
| "I'll add a few caveats to be safe." | Caveats that don't change the answer are noise. Mention one only if it matters. |

## Red Flags

- More than five bullets, or bullets that run to several sentences.
- Unexplained jargon or acronyms.
- The example is longer than the explanation.
- Facts that were made wrong to make them simpler.
- The reply opens with filler or ends without the offer to go deeper.

## Verification

- [ ] Starts with a one-line plain summary.
- [ ] Three to five short bullets, one idea each.
- [ ] Includes one tiny concrete example.
- [ ] Any technical word is defined in plain words.
- [ ] An analogy appears only if it helps understanding.
- [ ] Facts match the original answer or source.
- [ ] Ends with a one-line offer to go deeper.
