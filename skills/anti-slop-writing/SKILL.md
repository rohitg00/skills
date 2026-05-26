---
name: anti-slop-writing
description: Use when drafting, editing, or reviewing prose to remove AI-sounding patterns, generic filler, business jargon, forced drama, engagement bait, fake profundity, and formulaic social writing. Works for posts, essays, docs, launch copy, emails, and technical explanations.
---

# Anti-Slop Writing

Use this skill to make writing sound specific, human, and earned. The goal is not to make prose terse at all costs; the goal is to remove predictable AI texture while preserving the author's point, voice, and intent.

## Reference Files

For a deeper edit, load the targeted reference that matches the problem:

- `references/phrases.md`: phrase-level cleanup, banned openers, filler, jargon, softeners, and engagement bait.
- `references/structures.md`: structural tells such as binary contrast, negative listing, rhetorical scaffolding, false agency, passive voice, and rhythm problems.
- `references/examples.md`: before/after rewrites across social posts, launch copy, docs, email, personal writing, and community posts.

Use these references when the user asks for a strict anti-slop pass, when a draft still feels generic after the core workflow, or when you need examples before rewriting.

## When To Use

Use when the user asks to:

- remove AI slop.
- make writing sound human.
- tighten a draft.
- improve LinkedIn, Twitter/X, blog, README, launch, or email copy.
- review prose before publishing.
- rewrite content that feels generic, corporate, over-polished, or inflated.

Do not use when the user explicitly wants a formal corporate tone, legal language, academic style, or a deliberately promotional voice.

## Core Rewrite Rules

### 1. Start With The Point

Cut throat-clearing. The first sentence should carry information, not announce that information is coming.

Remove patterns like:

- "Here's the thing"
- "Let's talk about"
- "In today's world"
- "It is worth noting"
- "The reality is"
- "When it comes to"
- "At its core"

Replace them with the actual claim.

### 2. Kill Manufactured Drama

Avoid structures that pretend to reveal a twist.

Weak patterns:

- "Not X. Y."
- "X isn't the problem. Y is."
- "The answer isn't X, it's Y."
- "What if I told you..."
- "Let that sink in."
- "Full stop."

Better: state the claim directly. If contrast matters, write it as a normal sentence with concrete evidence.

### 3. Name The Actor

Passive voice and false agency make prose feel distant.

Weak:

- "Mistakes were made."
- "The decision emerged."
- "The market rewards this."
- "The culture shifted."

Better:

- "The team shipped the wrong fix."
- "The CTO chose the safer rollout."
- "Buyers paid for the simpler product."
- "Managers changed the incentives."

If no named actor exists, use "you", "teams", "buyers", "founders", "engineers", or another real subject.

### 4. Replace Jargon With Plain Words

Prefer short, concrete verbs.

| Weak | Better |
|---|---|
| utilize | use |
| leverage | use |
| navigate | handle |
| unpack | explain |
| landscape | market, field, situation |
| game-changer | meaningful change |
| deep dive | analysis |
| moving forward | next |
| circle back | return |
| align stakeholders | get people to agree |

Keep technical terms when they are accurate. Cut business fog.

### 5. Use Specifics

Generic claims sound machine-written because nothing can be checked.

Weak:

- "This improves productivity."
- "Developers need better tools."
- "The implications are significant."

Better:

- "This removes the 20-minute setup step."
- "Developers lose context when tickets, logs, and code live in three tabs."
- "A bad Gateway rollout can route production traffic to the wrong backend."

### 6. Vary Rhythm

AI prose often lands on a metronome: same sentence length, same paragraph shape, same punchy ending.

Use:

- short sentences for emphasis, not every line.
- longer sentences when explaining tradeoffs.
- one-item and two-item lists, not automatic triples.
- complete sentences more often than fragments.

Avoid stacks like:

- "Speed. Quality. Cost."
- "Build. Ship. Learn."
- "Simple. Fast. Reliable."

### 7. Cut Fake Quotables

If a line sounds like it wants to be screenshotted, test whether it says anything specific. Rewrite slogans into claims.

Weak:

- "The future belongs to builders."
- "Execution is the new moat."
- "Context is everything."

Better:

- "The team that ships the migration playbook first gets the enterprise deal."
- "Execution matters when competitors can copy the feature in a week."
- "The agent failed because it never saw the design decision from the last sprint."

## Editing Workflow

1. Identify the job: tweet, LinkedIn post, blog section, docs, email, launch copy, or general prose.
2. Preserve the core point. Do not flatten the author's opinion.
3. Remove throat-clearing and filler.
4. Replace vague claims with concrete details.
5. Remove formulaic contrast and fake drama.
6. Check passive voice and false agency.
7. Tighten rhythm.
8. Return a clean final version. If useful, add a short "changed" note.

## Slop Scan Checklist

Before final output, scan for:

- [ ] opener announces instead of saying.
- [ ] "not X, but Y" reveal structure.
- [ ] "let that sink in", "full stop", or similar emphasis crutch.
- [ ] vague words: important, powerful, significant, seamless, robust, transformative.
- [ ] business fog: leverage, unlock, navigate, landscape, game-changer.
- [ ] passive voice hiding the actor.
- [ ] inanimate noun doing a human action.
- [ ] three-item rhythm repeated.
- [ ] fake screenshot quote.
- [ ] unsupported superlative.
- [ ] engagement bait.

## Before / After Examples

### Generic Social Post

Before:

```text
Here's the thing: AI is changing how developers work. It is not about replacing engineers. It is about empowering them. Let that sink in.
```

After:

```text
AI changes the boring parts of engineering first: setup, search, scaffolding, and review prep. Engineers still own the decisions.
```

### Technical Claim

Before:

```text
In today's fast-paced DevOps landscape, teams need to leverage automation to unlock productivity.
```

After:

```text
Teams lose hours when deploys depend on tribal knowledge. Automating the release checklist removes that bottleneck.
```

### Launch Copy

Before:

```text
This tool is a game-changer for developers who want to streamline their workflow and boost productivity.
```

After:

```text
This tool remembers the decisions your coding agent forgot after compaction.
```

## Output Format

For rewrites:

```text
<final revised copy>
```

For reviews:

```text
Verdict: <publishable | needs revision>

Issues:
- <specific issue>

Rewrite:
<revised copy>
```

Keep the final answer focused. Do not explain every micro-edit unless the user asks.
