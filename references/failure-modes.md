# AI Roadmap Generation Failure Modes — Evidence from Case Studies

This file documents specific, verified failure modes observed when comparing AI-generated roadmaps
against expert-curated ones (e.g., roadmap.sh backend roadmap). Read this as a checklist of what
NOT to do.

## Failure Mode 1: Weight Error (everything is equally important)

**What AI does:** Lists all topics at the same visual/structural level.
**What experts do:** Use explicit tiers (roadmap.sh uses three colors: recommended / alternative / anytime).
**Why it matters:** If everything is important, nothing is. Weight IS the editorial judgment.

## Failure Mode 2: Stance Avoidance (the "it depends" cop-out)

**What AI does:** "Choose PostgreSQL or MySQL depending on your needs."
**What experts do:** "PostgreSQL (recommended). MySQL is a valid alternative."
**Root cause:** RLHF trains models to avoid offending anyone. Expert roadmaps get their value
precisely from having opinions.

## Failure Mode 3: Abstraction Level Mixing

**What AI does:** Puts "Learn React" and "Understand frontend architecture philosophy" at the same level.
**What experts do:** Keep each level homogeneous — all concepts, or all tools, not mixed.
**Why it matters:** Mixing levels makes it impossible to know what's fundamental vs derived.

## Failure Mode 4: Adjacent Domain Creep

**What AI does:** Includes "Data Structures & Algorithms" in a backend development roadmap.
**What experts do:** Exclude it — it's a CS fundamental prerequisite, not backend-specific content.
**Rule:** If a topic would appear in roadmaps for 3+ different domains, it's a prerequisite,
not domain content. Move it to the Prerequisites section.

## Failure Mode 5: Framework Laundry List

**What AI does:** Lists Django, Express, Spring, Rails, Laravel as separate roadmap nodes.
**What experts do:** Omit specific frameworks entirely — they're derived from language choice.
**Rule:** Frameworks are instances, not categories. Teach selection criteria, not exhaustive lists.

## Failure Mode 6: Cloud Service Inflation

**What AI does:** Lists "AWS / GCP / Azure" as a top-level learning category.
**What experts do:** Treat cloud as an implementation detail of deployment/infrastructure.
**Rule:** Cloud services are WHERE you deploy, not WHAT you need to understand architecturally.

## Failure Mode 7: Flat List (no ordering, no dependencies)

**What AI does:** Presents topics as a numbered list with no arrows or sequencing.
**What experts do:** Draw explicit prerequisite dependencies. "Relational Databases before APIs."
**Why it matters:** A roadmap without ordering is just a topic list. The ORDER is the roadmap.

## Failure Mode 8: Missing Boundaries (scope creep)

**What AI does:** Includes frontend basics in a backend roadmap, or complete DevOps pipeline
in a development roadmap.
**What experts do:** Explicitly state "see the [X] roadmap for this" — drawing clear boundaries.
**Rule:** Every roadmap must explicitly state what it does NOT cover.
