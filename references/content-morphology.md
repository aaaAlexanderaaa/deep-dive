# Content Morphology — Matching Output Structure to Domain Shape

Not every domain's knowledge fits the same container. The default output format (Prerequisites →
Core Path → Recommended → Elective → Disagreements → Exclusions) works well for **learning
progression** domains — where there is a natural sequence from foundational to advanced. But some
domains have a fundamentally different shape.

This file defines five content morphologies. In Phase 1, determine which morphology best fits the
domain, then choose (or adapt) the output structure accordingly.

**Critical rule:** The self-audit checklist (Phase 5) applies to ALL morphologies. Adapting the
output structure does not mean relaxing the editorial discipline. Stance, boundary, hierarchy,
subtraction, and source grounding are non-negotiable regardless of format.

---

## Morphology 1: Learning Progression (default)

**Shape:** Linear or DAG-shaped dependency chain. Topic B requires Topic A. There is a natural
"beginner → intermediate → advanced" arc.

**Best structure:** The default output format — Prerequisites → Core Path → Recommended Extensions
→ Elective.

**Signals that this is the right morphology:**
- The domain has textbooks with chapter orderings
- Certification paths exist (implying sequenced levels)
- There is a clear "you can't understand X without Y" relationship between topics

**Examples from observed output:** Complexity science roadmap (dynamical systems → chaos → emergence
→ CAS → network science). Writing craft roadmap (clarity → density → voice → structure).

---

## Morphology 2: Operational Protocol

**Shape:** Decision tree or checklist. The goal is not understanding but execution. Order matters
because it determines physical sequence, not conceptual dependency.

**Best structure:** Numbered steps, decision points, safety constraints, and quick-reference cards.
Replace "Core / Recommended / Elective" with "Always do / Situational / Never do."

**Signals that this is the right morphology:**
- The domain produces a physical action sequence (exercise routine, manufacturing process, triage)
- "Correctness" means "safe and effective execution," not "deep understanding"
- The user's goal is to NOT think, not to think deeply

**Adaptation from default format:**
- Prerequisites → **Safety prerequisites & contraindications**
- Core Path → **Fixed-order protocol** (numbered, no branching)
- Recommended → **Situational modifications** (when to deviate from the protocol)
- Elective → Drop entirely or replace with **Progression path** (how to advance after mastery)
- Disagreements → **Competing protocols** (if applicable)
- Exclusions → Keep (still valuable to say what this protocol does NOT cover)

**Example from observed output:** Programmer stretching protocol — zero-decision design, fixed
sequence, safety red lines.

---

## Morphology 3: Argumentative / Diagnostic

**Shape:** Causal chain or thesis-evidence structure. The goal is not to list topics but to build
a coherent argument or diagnosis. The structure IS the argument.

**Best structure:** Thesis statement → causal layers (each layer is a section) → evidence anchors
→ strongest counterarguments → implications. The "Core / Recommended / Elective" distinction
applies not to topics but to layers of the causal chain (which layers are essential to the
argument vs. supporting).

**Signals that this is the right morphology:**
- The domain is a "why" question, not a "what" or "how" question
- The user wants to understand a phenomenon, not learn a skill
- There is an identifiable thesis that can be wrong (falsifiable)

**Adaptation from default format:**
- Prerequisites → **Conceptual prerequisites** (what frameworks you need to follow the argument)
- Core Path → **Causal chain** (ordered by causation, not by learning difficulty)
- Recommended → **Supporting evidence & case studies** (concrete anchors for abstract layers)
- Elective → **Adjacent diagnoses** (related arguments that illuminate but are not required)
- Disagreements → **Steelman counterarguments** (essential — an uncontested diagnosis is suspect)
- Exclusions → **Prescriptions this diagnosis does NOT offer** (important: diagnosis ≠ treatment)

**Example from observed output:** Modern predicaments roadmap v3 — six-layer causal chain from
"collapse of futurity" to daily experience, with fieldwork vignettes as evidence anchors.

---

## Morphology 4: Reference / Lookup

**Shape:** Flat or shallow hierarchy optimized for search, not sequential reading. The user comes
with a specific question and needs to find the answer quickly, not read front to back.

**Best structure:** Categorized index → expandable sections → cross-references. Replace the
learning path with a lookup structure. Add a "quick reference card" or "cheat sheet" at the top.

**Signals that this is the right morphology:**
- The domain is a tool, platform, or API (not a conceptual field)
- Users will return to this document repeatedly for specific lookups
- There is no meaningful "you must learn A before B" ordering for most content

**Adaptation from default format:**
- Prerequisites → **What you should already know to use this tool**
- Core Path → **Essential concepts** (keep short — only the mental model needed to use the tool)
- Recommended → Replace with **Categorized reference** (grouped by task type, not importance)
- Elective → Replace with **Advanced patterns / power-user features**
- Add: **Quick reference card** at the top (most common operations in a compact table)
- Add: **Suggested learning path** at the bottom (for users who DO want sequential learning)

**Example from observed output:** Claude Code deep dive — a tool documentation topic that was
generated using the default learning-progression format. It worked but could have been more
effective as a lookup-first document with a learning path appendix.

---

## Morphology 5: Iterative / Dialectical

**Shape:** Not a progression from A to Z, but a series of attempts, failures, and refinements.
The final position is meaningful only because you can see what was tried and rejected.

**Best structure:** Version history or dialectical structure — thesis → antithesis → synthesis,
or iteration 1 → what broke → iteration 2 → what broke → current position. The process IS the
content.

**Signals that this is the right morphology:**
- The domain has no settled consensus — the state of the art is a moving target
- The most valuable insight is "why naive approaches fail," not "what the right answer is"
- The author has gone through actual iterations of understanding and the trajectory matters

**Adaptation from default format:**
- Prerequisites → Keep (what you need to follow the argument)
- Core Path → Replace with **Iteration record** (each iteration: thesis → challenge → revision)
- Recommended → **Stable conclusions** (what survived all iterations)
- Elective → **Open questions** (what remains unresolved)
- Disagreements → Integrate into the iteration narrative (disagreements are what drive iterations)
- Exclusions → Keep

**Example from observed output:** AI-era software architecture methodology — four iterations, each
overturned by a sharper question, concluding with "there is no universal solution." The iteration
record is more valuable than any single iteration's conclusion.

---

## How to choose

In Phase 1, after determining audience and scope, ask:

> "If I imagine the ideal reader using this document, are they:
> (a) Learning a subject from scratch? → **Learning Progression**
> (b) Following a procedure step by step? → **Operational Protocol**
> (c) Trying to understand why something is the way it is? → **Argumentative / Diagnostic**
> (d) Looking up a specific answer? → **Reference / Lookup**
> (e) Watching a position evolve through challenge? → **Iterative / Dialectical**"

Many domains are hybrids. When in doubt, default to Learning Progression (the default format) —
it is the safest choice. Only deviate when the morphology mismatch is clear enough that the
default would produce a noticeably worse document.
