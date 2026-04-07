# Editorial Audit — Failure Modes That Pass Structural Review

The `failure-modes.md` file documents **structural** failures: wrong hierarchy, missing boundaries,
no stance. This file documents a different class of problems: roadmaps that pass every structural
check but still feel mediocre to read. These are editorial-layer failures — they live in the prose,
not in the architecture.

These failure modes were identified by auditing 13 roadmaps produced by this skill across domains
ranging from complexity science to writing craft to software architecture.

---

## Editorial Failure Mode 1: Emphasis Overload

**What happens:** Nearly every paragraph contains 2-3 bold phrases. The AI uses bold to signal
"this is my key judgment" — but when every judgment is bolded, the visual hierarchy collapses.

**Why AI does this:** The model wants to be helpful and highlight important points. But emphasis
is a scarce resource — spending it everywhere devalues it.

**What good looks like:** ≤3-5 bold phrases per 1000 words. When a point truly deserves emphasis,
use structural means instead of typographic means:
- Promote it to a heading or sub-heading
- Give it its own paragraph (a one-sentence paragraph is inherently emphatic)
- Use a blockquote or callout
- Place it as the first or last sentence of a section (position creates emphasis)

**Audit rule:** After drafting, scan for bold text. If a section has more than 5 bold phrases,
force-rank them: keep the top 3, convert the rest to plain text. If any demoted phrase still feels
critical, it probably deserves structural elevation, not bold.

---

## Editorial Failure Mode 2: Reassurance Drift in Conclusions

**What happens:** The body of the roadmap makes sharp, opinionated judgments. But the conclusion
softens into generic reassurance: "This is a challenging journey, but it's worth it," "There are no
easy answers, but understanding the landscape is the first step," "The path isn't linear, but
persistence pays off."

**Why AI does this:** RLHF training rewards endings that leave the user feeling good. The model
has learned that sharp conclusions can feel abrupt or discouraging, so it defaults to a warm,
supportive close. This is the "it depends" failure mode (Failure Mode 2 in `failure-modes.md`)
reappearing at the paragraph level — the model has been trained not to hedge on recommendations,
but the hedging instinct resurfaces in the conclusion as emotional softening.

**What good looks like:** The conclusion should be the sharpest paragraph in the document. Options:
- **Restate the core thesis without softening.** "There is no universal architecture. The only honest
  answer is: it depends on where you are, and it will change." (from AI Architecture Methodology)
- **End on an unresolved tension.** Don't resolve what the body left unresolved — let the reader
  sit with it.
- **End with a concrete implication.** Not "this matters" but "this means X will happen if you do Y."

**Audit rule:** Read the last paragraph. Does it contain any of these phrases or their equivalents?
- "This is hard/challenging but worth it / rewarding"
- "The journey is the destination"
- "There are no easy answers, but..."
- "With persistence / practice / time, you will..."
- "The first step is always the hardest"

If yes, rewrite. The conclusion earned by a sharp body is a sharp conclusion, not a hug.

---

## Editorial Failure Mode 3: Source Homogeneity

**What happens:** The roadmap cites 5-10 sources, but all sources share the same fundamental
stance. The triangulation (Phase 2B) achieves cross-disciplinary coverage but not
cross-positional coverage.

**Example from observed output:** A "modern predicaments" roadmap cited Rosa (acceleration theory),
Hartog (presentism), Fisher (capitalist realism), Han (burnout society), Chang (compressed modernity),
and Meadows (systems thinking). Six sources, four disciplines — but all belong to the "modernity
critique" tradition. Missing: economists who argue growth continues (Tyler Cowen), demographers who
show fertility recovery is possible (Israel, Georgia), sociologists who document resilient community
structures (Chinese community group-buying, plaza dancing, clan networks).

**Why AI does this:** The model gravitates toward sources that form a coherent narrative. Introducing
a source that contradicts the thesis feels like undermining the roadmap's authority. But a roadmap
that only cites agreeing sources is not triangulated — it's an echo chamber with academic footnotes.

**What good looks like:** For every core thesis, include at least one source that represents the
strongest available counterargument (steelman, not strawman). Then explain why you maintain your
position despite this counterargument. This makes the roadmap MORE authoritative, not less — it
shows the author has considered and addressed the opposition.

**Audit rule:** List the sources. For each one, mark whether it AGREES, DISAGREES, or is NEUTRAL
toward the roadmap's core thesis. If no source disagrees, actively search for the strongest
counterargument and add it to the "Structural Disagreements" section.

---

## Editorial Failure Mode 4: Template Ossification

**What happens:** Every roadmap uses the exact same Markdown section structure regardless of
whether the domain's knowledge naturally fits that shape. The Prerequisites → Core → Recommended →
Elective → Disagreements → Exclusions structure becomes a form to fill rather than a structure
that serves the content.

**Why AI does this:** The skill provides a specific output format, and the model follows it
literally. This is usually correct — the format encodes hard-won editorial discipline. But when
the content morphology doesn't match the format, literal compliance produces worse output than
thoughtful adaptation.

**When this is a real problem vs. when it's fine:**
- Fine: knowledge domains with natural learning progressions (complexity science, backend development)
- Problem: operational protocols (stretching routines — no "elective" stretches), reference manuals
  (tool documentation — lookup-first, not path-first), argumentative essays (no "core vs elective"
  distinction — the argument is the structure)

**What good looks like:** The format's SPIRIT (stance, boundary, hierarchy, exclusions) is
non-negotiable. The format's LETTER (specific section names and ordering) can adapt to content
morphology. See `content-morphology.md` for the morphology taxonomy.

**Audit rule:** After choosing the output structure, verify that every section contains substantive
content, not filler. If a section exists only because the template has a slot for it (e.g.,
"Prerequisites: basic literacy" in a writing roadmap), either give it real content or remove it.
