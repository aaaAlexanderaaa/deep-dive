---
name: deep-dive
description: >
  Generate an expert-quality, opinionated knowledge roadmap for any domain — with correct hierarchy,
  correct dependencies, correct weights, and deliberate omissions. Use this skill whenever the user
  asks to "deeply understand", "learn from scratch", "get the big picture of", "深入浅出", "系统性地学习",
  "give me a roadmap for", "what should I learn about X", "help me understand X end to end",
  or any request that implies building structural understanding of a domain rather than answering
  a specific factual question. Also use when the user says "从零开始学", "帮我梳理", "全景图", "知识体系".
  Do NOT use for simple factual Q&A — only for requests that need a structured, hierarchical overview.
---

---

# Deep Dive — Expert-Quality Knowledge Roadmap Generator

> **Edit mode.** If the task description names specific pages to fix, references a parent task's review record, or enumerates a narrow allow/deny list of changes (callout / parent move / link replacement / index restructure / archive / compression), this skill is in edit mode: treat Phase 2 (source curation) as advisory rather than mandatory, do not create new pages or v2 / 修正版 unless explicitly authorized, and apply Phase 5 self-audit to your edits rather than the whole page. The task description's allow/deny lists override anything in this skill where they conflict.
> 

---

## Why this skill exists

AI has expert-level knowledge but not expert-level thinking. When asked to "explain X deeply" or
"give me a roadmap for Y", AI's default behavior produces output that looks comprehensive but fails
in three specific ways:

1. **No stance** — AI hedges ("it depends on your needs") instead of making opinionated recommendations
2. **No boundary** — AI adds everything tangentially related instead of knowing what to exclude
3. **No hierarchy** — AI lists everything at the same level instead of distinguishing core from optional

These failures stem from a structural gap called the "compositionality gap": AI knows each fact
individually but cannot compose them into a coherent, opinionated architectural judgment. This skill
exists to counteract these defaults through a disciplined process.

## Core principle: Curate, don't generate

Do NOT generate knowledge structures from your training data alone. Instead:

1. **Find** existing expert-curated structures (BoKs, syllabi, certification paths, [roadmap.sh](http://roadmap.sh/), awesome-lists)
2. **Extract** their skeleton
3. **Align** multiple sources to find consensus and identify structural disagreements
4. **Synthesize** with editorial judgment — take a stance, draw boundaries, control hierarchy

The reason: expert roadmaps get their quality from years of community debate about what to EXCLUDE.
You cannot replicate that debate. But you can read its output.

---

## Process

### Phase 1: Understand the request (do NOT skip)

Before producing anything, determine:

1. **Target audience and goal** — Who is this for? A career switcher? A senior engineer exploring
an adjacent domain? A student? The same domain has completely different roadmaps for different
audiences. If the user hasn't specified, ask ONE clarifying question. Do not proceed without a
stance on audience.
2. **Domain type (Cynefin)** — Is this domain:
    - **Established** (textbooks exist, certification paths exist, BoKs exist)? → Lean heavily on
    existing structures.
    - **Emerging/frontier** (no textbooks yet, knowledge is in blog posts and papers)? → Use the
    triangulation approach (Phase 2B).
3. **Scope boundary** — What is explicitly NOT part of this roadmap? Define this BEFORE generating
anything. Example: a "Backend Development" roadmap should exclude data structures & algorithms
(that's CS fundamentals, not backend-specific) and specific frameworks (those are derived from
language choice).
4. **Content morphology** — What is the natural shape of knowledge in this domain? Not every domain
fits the default "learning roadmap" structure. Before choosing an output format, determine the
morphology. See [Content Morphology — Matching Output Structure to Domain Shape](./references/content-morphology.md)  for the taxonomy. If the morphology calls for
a different structure than the default output format, adapt accordingly — the self-audit checklist
(Phase 5) still applies regardless of output structure.
5. **Task shape check** — Before choosing a roadmap format, decide whether the user is asking for:
    - **Learning roadmap** — What should someone learn, and in what order?
    - **Knowledge map** — What are the main parts of a domain, and how do they relate?
    - **Mechanism analysis** — What produces the observed pattern?
    - **Concept audit** — What assumptions, definitions, or evaluation standards are hidden inside a concept?

If the request is not a learning roadmap, do not force it into the default roadmap output. Use the structure that best fits the task.

### Before source curation: check whether existing structures are part of the problem

Expert-curated sources are usually valuable, but they can also preserve the field’s existing blind spots. Before treating a Body of Knowledge, syllabus, certification path, or roadmap as authoritative, ask:

- What does this structure make central?
- What does it treat as optional or peripheral?
- What does it leave out entirely?
- Whose practical experience would not fit inside this structure?

Do not reject expert structures by default. Use them, but audit their boundaries.

### Phase 2A: Find and extract expert-curated structures (for established domains)

Search for and retrieve at least 2-3 of these, in priority order:

1. **Bodies of Knowledge** — CS2023, SWEBOK, PMBOK, DAMA-DMBOK, CFA curriculum, or equivalent for
the domain. These are the gold standard — expert committees spent years curating them.
2. [**roadmap.sh**](http://roadmap.sh/) — Check if [roadmap.sh](http://roadmap.sh/) has a roadmap for this domain. If yes, fetch it.
3. **University syllabi** — Search for top university course sequences in this domain.
4. **Certification paths** — AWS/GCP/Azure paths, professional certifications, etc.
5. **Awesome lists** — Search GitHub for `awesome-[domain]`. These are community-curated.
6. **Survey papers** — Search for "[domain] survey" or "[domain] systematic review" on
Semantic Scholar or Google Scholar.

For each source found:

- Extract the **top-level structure** (major categories/modules)
- Note what each source **excludes** (this is as informative as what it includes)
- Note any **prerequisite orderings**

### Phase 2B: Triangulation (for emerging/frontier domains or when BoKs don't exist)

When no authoritative structure exists:

1. Search for 3+ sources with **different perspectives** on the domain (academic, industry, open-source).
"Different perspectives" means **different stances**, not just different disciplines. At least one
source should challenge or contradict the emerging thesis. If you can only find sources that agree,
state this explicitly — consensus is informative, but so is the absence of opposition.
2. Map each source's claims about what the domain contains
3. **Intersection** of all sources = high-confidence core
4. Items in only one source = needs verification, likely peripheral
5. Items none mention but "should be there" = potential blind spots to flag

### Phase 3: Alignment and conflict detection

Compare the structures you found:

1. **Consensus nodes** — concepts that appear in all sources → these are your core
2. **Disputed nodes** — concepts that some sources include and others exclude → mark these as
"contested" and explain the disagreement. Do NOT silently pick a side.
3. **Ordering disagreements** — where sources disagree on prerequisites → flag these and explain
why different orderings make sense for different audiences
4. **Weight disagreements** — where sources disagree on importance → use the Meadows leverage
point framework: concepts about *why* (paradigms, principles) outweigh concepts about *how*
(tools, APIs)
5. **False consensus** — Cases where multiple sources use the same word but mean different things. Do not merge these too quickly. Name the different meanings.
6. **Missing categories** — Cases where a recurring experience, failure mode, or practical problem appears in examples but has no stable place in the official structure.
7. **Hidden evaluation standard** — Cases where a source ranks something as "basic," "advanced," "professional," "mature," or "best practice" without making the underlying standard explicit.

### Phase 4: Synthesis — produce the roadmap

Now produce the actual output. Apply these editorial rules:

**Stance rule:** For every node where a reasonable recommendation exists, MAKE ONE. Say "PostgreSQL
(recommended)" not "PostgreSQL or MySQL, depending on your needs." If you genuinely cannot
recommend, explain why the choice is context-dependent and what the deciding factors are.

**Boundary rule:** For every node, ask: "Is this specific to this domain, or is it a general
prerequisite?" General prerequisites go in a separate "Prerequisites" section, not in the main
roadmap. Example: "Data Structures & Algorithms" is a prerequisite for backend development, not
a part of it.

**Hierarchy rule:** Every node must be classified into one of three tiers:

- **Core** — You must understand this. Not optional.
- **Recommended** — Important for most practitioners. Learn after core.
- **Elective** — Valuable in specific contexts. Learn when relevant.

**Dependency rule:** Draw explicit prerequisite arrows. "To understand X, you need Y first." Do
NOT present the roadmap as a flat list. If you are unsure about ordering, say so — but still
propose an ordering rather than leaving it ambiguous.

**Subtraction rule:** After drafting, review every node and ask: "If I remove this, does the
roadmap still make sense for the target audience?" If yes, remove it or downgrade it to Elective.
The goal is the MINIMUM structure that captures the essential shape of the domain.

### Phase 5: Self-audit (do NOT skip)

Before presenting the roadmap, check it against these known AI failure modes:

- [ ]  **Stance check:** Did I actually recommend specific choices, or did I hedge with "it depends"?
- [ ]  **Boundary check:** Is anything in here that belongs to an adjacent domain rather than this one?
- [ ]  **Hierarchy check:** Are all nodes at the same level, or did I actually differentiate core/recommended/elective?
- [ ]  **Abstraction consistency:** Are nodes at the same level the same TYPE of thing? (Don't mix
"Learn React" with "Understand frontend architecture philosophy" at the same level)
- [ ]  **Prerequisite check:** Did I specify what comes before what, or is this a flat list?
- [ ]  **Task-shape check:** Did I choose the right output shape, or did I force a non-roadmap task into a roadmap?
- [ ]  **Boundary audit:** Did I check what the main sources exclude, not just what they include?
- [ ]  **False-consensus check:** Did I merge terms that look similar but mean different things in different sources?
- [ ]  **Hidden-standard check:** When I use labels like "core," "advanced," "mature," or "best," did I explain the standard behind the label?
- [ ]  **Subtraction check:** Can I remove any node without loss? If so, remove it.
- [ ]  **Source check:** Is this roadmap grounded in expert-curated sources, or did I generate it
purely from training data?
- [ ]  **Adversarial source check:** Do my sources include at least one perspective that challenges
my core thesis? If all sources agree with each other, I may be in an echo chamber.
(See [Editorial Audit — Failure Modes That Pass Structural Review](./references/editorial-audit.md)  § Source Homogeneity)
- [ ]  **Emphasis density check:** Is bold/italic text used sparingly (≤3-5 per 1000 words)? When
everything is emphasized, nothing is. If over-dense, promote the most important points to
structural emphasis (headings, pull-quotes, standalone paragraphs) and de-bold the rest.
- [ ]  **Closing sharpness check:** Does the conclusion maintain the same intellectual sharpness as
the body? AI defaults to softening conclusions with reassurance ("this is hard but worth it").
The conclusion should be the sharpest paragraph, not the gentlest.
- [ ]  **Edit-mode check:** If this is an edit / correction / structural task, did I respect the task description's "唯一允许修改 / 禁止修改" lists and skip Phase 2 research?
- [ ]  **China-context source gate:** If the topic is China-bound, are ≥ 50% of cited sources Chinese-language primary or scholarly? If a sub-topic falls short, did I document which keywords / databases I searched and why no source qualified — instead of default-skipping?
- [ ]  **Visualization morphology check:** For every multi-object × multi-dimension comparison, multi-century / multi-stage timeline, and abstract causal chain — is there a table / timeline / mechanism diagram serving that specific argument? Decoration figures do not count.
- [ ]  **Table integrity & foreign-term hygiene:** Does each table's header column count match every row's cell count? Are first-occurrence foreign names / book titles / terms given as 「中文译名（English Original）」, with a 1–2 sentence mechanism explanation when the term carries argumentative weight (acronym expansion alone is not enough)?

If any check fails, fix it before presenting.

---

## Output format

If the task is not a learning roadmap, adapt the output format. Examples:

- For a **concept audit**: define the concept, identify competing meanings, expose hidden standards, show conflicts.
- For a **mechanism analysis**: describe the observed pattern, identify causes, map feedback loops, state failure points.
- For a **knowledge map**: show major regions, boundaries, dependencies, and contested areas.
- For a **decision guide**: define the decision, compare options, name trade-offs, give a recommendation.

The default roadmap template applies only when the user is asking what to learn and in what order.

Structure the output as:

```markdown
# [Domain] Roadmap

> **Target audience:** [who this is for]
> **Scope:** [what's included]
> **Explicitly excluded:** [what's NOT included and why]
> **Sources consulted:** [list of BoKs, syllabi, roadmaps used]

## Prerequisites
[Things the learner should already know — these are NOT part of this domain]

## Core Path
[Ordered sequence of must-learn topics, with dependency arrows]

## Recommended Extensions
[Important but not strictly necessary — organized by sub-domain]

## Elective / Context-Dependent
[Valuable in specific situations — with notes on WHEN each is relevant]

## Structural Disagreements
[Where expert sources disagree — what the debate is and why it matters]

## What This Roadmap Intentionally Excludes
[Explicit list of things a naive generator would include but this roadmap doesn't, with reasons]
```

---

## Anti-patterns to avoid

These are the specific mistakes that make AI-generated roadmaps mediocre. If you catch yourself
doing any of these, stop and correct:

1. **The "everything is important" trap** — Listing 30 topics all at the same level. If everything
is important, nothing is. Force yourself to have no more than 7±2 core nodes.
2. **The "it depends" cop-out** — Refusing to recommend because "different people have different
needs." The user asked YOU for a roadmap. Take a stance. You can note alternatives, but lead
with a recommendation.
3. **The tool-vs-concept confusion** — Listing "Docker" and "Containerization Philosophy" at the
same level. Tools are instances of concepts. Concepts go in the roadmap; tools go as
recommended implementations under concepts.
4. **The adjacent-domain creep** — Including "data structures and algorithms" in a backend roadmap,
or "color theory" in a UI engineering roadmap. These are prerequisites, not part of the domain.
5. **The framework laundry list** — Listing every framework (Django, Express, Spring, Rails, Laravel)
instead of teaching the user how to evaluate and choose one. Frameworks are derived from more
fundamental choices.
6. **The flat list** — Presenting topics without ordering or dependency. A roadmap without arrows
is just a topic list.
7. **The missing "why"** — Listing WHAT to learn without explaining WHY it matters and WHERE it
fits in the larger picture.

---

## Reference: Meadows Leverage Point Framework for weight allocation

When deciding what matters more, use this hierarchy (from least to most impactful):

| Weight | Level | In learning terms | Example |
| --- | --- | --- | --- |
| Low | Parameters | Memorizing an API's parameter names | `docker run -p 8080:80` |
| Low-Med | Buffers/Structure | Understanding how a tool works | How Docker containers work |
| Med-High | Feedback loops | Understanding trade-offs and when things break | Monolith vs microservice trade-offs |
| High | Rules/Self-organization | Understanding why a paradigm exists | Why containerization emerged |
| Highest | Goals/Paradigms | Understanding what problem the domain solves | Why we need backend development at all |

Prioritize higher-leverage knowledge. A roadmap full of parameters-level content is low quality
even if technically accurate.
