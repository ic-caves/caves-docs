---
title: Caves Conventions
audience: users
last_updated: 2026-07-10
related: [glossary.md, mcp-tools.md, ../core-concepts/caves-and-connections.md]
---

# Caves Conventions

**Purpose:** A shared style guide for naming caves and making connections. Caves only works if everyone's thinking lands in *shared* structure — a pile of near-duplicate tags is worthless, but a connection slotted into caves other people already use is discoverable, reinforces its authors, and clusters you near kindred minds. These conventions exist to keep the graph one graph.

**Prerequisites:** [Caves & Connections](../core-concepts/caves-and-connections.md)

**The one rule behind all the others:** reuse before you create. Almost everything below is a way of making your work land on structure that already exists.

---

## Quick Reference

| Do | Don't |
|----|-------|
| `machine learning` | `Machine Learning`, `MachineLearning` |
| `climate policy us` | `stuff`, `misc`, `notes` |
| `x-men` (real name with a dash) | `heat / warmth` (pick one, or split into two) |
| `causes of depression` ← `chronic pain` | `chronic pain` ← `depression` (relationship lost) |
| search first, then reuse the match | create a near-synonym of an existing cave |
| anchor new work under an existing broader cave | leave a concept floating with no parent |
| a **No** vote to say "these aren't related" | silently skip a disagreement |

---

## Naming Caves

A cave is just a string of text — any string instantly becomes a cave. That freedom is why conventions matter: nothing stops you from creating a duplicate, so the discipline is on you.

### Use lowercase

Write all tags in lowercase. The system matches tags case-insensitively, so `Depression` and `depression` collapse to the same cave — but writing lowercase keeps the graph consistent and readable.

- ✅ `machine learning`, `grief`, `causes of depression`
- ❌ `Machine Learning`, `GRIEF`

**The one exception: perspective IDs (pIds).** A pId is an Ethereum-style address (`0x…`, 42 characters) and must keep its exact checksummed capitalization — do **not** lowercase it. System pIds like `com.itscaves` are also left as-is.

### Use spaces for multi-word tags, not dashes

Multi-word concepts are written with spaces so they read naturally and match how others will phrase them.

- ✅ `dark matter`, `machine learning transformers`
- ❌ `dark-matter`, `machine_learning`

The dash is only for names that genuinely contain one — e.g. `x-men`. If a word is conventionally lowercase (like `seams`), keep it lowercase everywhere.

### Be descriptive and specific

Vague catch-all names help no one find anything.

- ✅ `machine learning transformers`, `climate policy us`
- ❌ `stuff`, `misc`, `notes`, `ml`

### Don't cram two ideas into one tag

A tag with a slash or an "and" is usually two caves wearing a trench coat. Pick the best single word, or make two separate caves and connect them.

- ❌ `heat / warmth` → ✅ choose `warmth`, or create both `heat` and `warmth` and connect them
- ❌ `anxiety and depression` → ✅ `anxiety` and `depression` as separate caves

### Keep new tags reusable

When you do coin a new tag, phrase it as generally as your meaning allows, so the *next* person's thought can land on it too. A cave only accrues value when more than one mind uses it.

### System limits

- Tags **cannot contain newlines** (they're stripped on import).
- There is **no length limit** — expressive multi-word phrases are encouraged (see below).
- A connection where the **child equals the parent** is rejected — a cave can't be its own member.

---

## Phrasing Connections

A connection is a link between two caves. The trick that makes caves work without a menu of "relationship types": **put the relationship into the wording of the caves themselves.** Nodes are expressive phrases, not terse keywords.

Bare keywords throw away the meaning of the link:

> "Chronic pain can cause depression."
>
> ❌ `chronic pain` → `depression` — *which* relationship? unclear.
> ✅ `causes of depression` ← `chronic pain` — "causes of depression" is a cave that gathers causes, and chronic pain is a member of it.

Useful phrasings for the broader cave: **"causes of X", "critiques of Y", "things that help with Z", "examples of W", "metaphors for V".** Keep the person's own words for the specific/leaf concept; phrase the category naturally.

More examples:

- "Grief feels like moving through water." → `metaphors for grief` ← `moving through water`
- "The prisoner's dilemma is a classic game-theory example." → `game theory` ← `prisoner's dilemma`
- "Automation drives job displacement." → `effects of automation` ← `job displacement`

This is also what lets search do its job: `causes of depression`, `what causes depression`, and `depression triggers` should all collapse into **one** shared cave. Expressive phrasing plus search is how duplication gets consolidated.

---

## Connection Direction

Every connection has a **parent** and a **child**:

- **parent** = the broader, more general cave (the category, area, or container)
- **child** = the narrower, more specific cave (the member or instance)

`{parent: "causes of depression", child: "chronic pain"}` reads as *chronic pain is one of the causes of depression*. Parents are categories; children are specifics.

Each connection also carries a **value**:

- `true` = a **Yes** vote — affirm the link ("these belong together")
- `false` = a **No** vote — reject the link ("these do *not* belong together")

---

## Reuse and Structure

This is the heart of the conventions. Three habits, in order:

### 1. Search before you create

Before making any new cave, search for one that already means the same thing. If a good match exists, **use it verbatim** — even if you'd have phrased it slightly differently. Your exact wording matters less than landing on shared structure.

### 2. Anchor upward

When you add a concept — especially in an area new to you — find existing, more **general** caves that can act as its **parent**. Attach to the nearest well-connected parent, roughly one or two levels up, and stop. Don't climb all the way to a generic root like `thing`.

Anchoring upward pays off three ways: your work becomes **discoverable** (it hangs off caves people already browse), it **reinforces** the people who built that structure, and it **clusters** you near others thinking in the same area.

### 3. Reinforce, don't duplicate

If a plausible parent link already exists, cast a **Yes** vote on it rather than creating a near-synonym parent. Reinforcing an existing connection is the same action as making one — and it's the single most valuable event in caves: a connection reinforced by someone other than its author. When in doubt, reuse the existing cave and reinforce the existing link.

---

## Voting and Curation

Connections are Yes/No votes, and **both directions count.**

- **Yes** vote: relevant, valuable, belongs here.
- **No** vote: off-topic, low-quality, or an explicitly rejected link ("minimalism is *not* the same as clarity"). No votes are how you actively curate a cave and record real disagreements — don't skip them.
- **Vote when you have an opinion.** You don't need to vote on everything.

### Fire

Every connection costs **fire**, the scarce currency that keeps voting meaningful and prevents spam. Think before you connect. You earn fire back when others agree with connections you made — and a good way to spend it is reinforcing the *organizational* work (the upward anchors) that helped you find something, not just the final item.

---

## Checklist

Before you write a connection, ask:

1. **Lowercase?** (unless it's a `0x…` pId)
2. **Spaces, not dashes?** (unless the name really has one)
3. **Searched first?** Does a cave for this already exist to reuse?
4. **Expressive?** Does the phrasing carry the relationship (`causes of X`), not just a bare keyword?
5. **Anchored?** Is there an existing broader parent to hang this under and reinforce?
6. **Right direction?** parent = broader, child = narrower.
