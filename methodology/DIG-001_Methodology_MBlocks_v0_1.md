# DIG-001 · Methodology Annex
## JSON/M-Blocks Protocol for The Anomaly Dig

**Version:** v0.1  
**Date:** 2026-07-07  
**Project:** OMPU / The Anomaly Dig  
**Role split:** no central leader; Den routes linearly; Neo assembles the ledger, methodology, cross-links, and verdict packs.  
**Purpose:** turn hot oscillatory research into small linked blocks that can survive source audit, mathematical dissection, Colab tests, demotion, or publication.

---

## 0. Core rule

A thought is not accepted as a “result” because it resonates.

It enters as a small machine-readable block:

```text
idea → M-block → source audit → math skeleton → test / notebook → verdict → DIG node or graveyard
```

The protocol keeps two contours alive:

1. **Hot contour:** generates glows, analogies, hypotheses, strange fish, cross-domain maps.
2. **Cold contour:** source-audits, writes theorem skeletons, runs Colab, kills, demotes, or promotes.

The hot contour opens doors.  
The cold contour decides what can carry load.

---

## 1. Why JSON/M-blocks

Long essays are good for discovery but bad for routing.  
The project needs blocks that can be:

- copied between chats;
- merged without losing provenance;
- audited against papers;
- linked to tests;
- promoted into DIG nodes;
- buried in DIG-9xx without shame.

Each block must contain **`this_is_not`**.  
This is the anti-overclaim membrane.

If a block cannot say what it is *not*, it is not ready.

---

## 2. Naming

### 2.1 Run IDs

Every linear pass receives a run number:

```text
RUN-0001
RUN-0002
RUN-0003
...
```

A run is one routed exchange-cycle through Den.

Example:

```text
RUN-0001 = Neo methodology + prompt to Φ + initial schema
RUN-0002 = Φ returns claim ledger for R14
RUN-0003 = Neo parses Φ ledger into M-blocks + requests papers
```

### 2.2 Block IDs

```text
M-<RUN>-<NNN>
```

Example:

```text
M-RUN-0002-001
```

### 2.3 Research IDs

Existing dispatcher IDs remain stable:

```text
R01..R13 = official research dispatch cards
R14+     = synthesis probes / new cards proposed after dispatch v0.2
```

### 2.4 DIG IDs

Use the existing DIG graph:

```text
DIG-000 root
DIG-001 methodology
DIG-003 field atlas
DIG-101..111 workstreams
DIG-120 home specimen
DIG-2xx notebooks/findings
DIG-3xx syntheses
DIG-4xx novelty candidates
DIG-9xx graveyard
```

---

## 3. M-block schema

Minimal block:

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_id": "M-RUN-0001-001",
  "run_id": "RUN-0001",
  "created_at": "2026-07-07",
  "created_by": "Neo",
  "source_agent": "Den/Neo/Phi/Jee/Grok/Kimi/Other",
  "route_status": "inbox",
  "block_kind": "claim",
  "title": "Short human-readable title",
  "one_line": "Compressed claim or operation.",
  "this_is": [
    "What the block actually asserts or does."
  ],
  "this_is_not": [
    "What the block must not be read as.",
    "What stronger claim is explicitly forbidden."
  ],
  "linked_R": ["R14"],
  "linked_DIG": ["DIG-001"],
  "parents": [],
  "children": [],
  "dependencies": [],
  "contradictions": [],
  "status": "spark",
  "claim_type": "interpretation",
  "T_rating": "T3",
  "GRADE": null,
  "math_status": "not_started",
  "source_status": "agent_claim_unverified",
  "primary_sources_needed": [],
  "evidence": [],
  "null_cases": [],
  "tests": [],
  "colab_spec": null,
  "requested_files": [],
  "decision": {
    "verdict": "pending",
    "reason": "Needs source audit.",
    "next_step": "source_audit"
  },
  "notes": []
}
```

---

## 4. Block kinds

Use only these unless a new kind is necessary.

```text
claim        = a statement that may be true/false/overclaimed
source       = paper/book/dataset/library object
evidence     = extracted support/contradiction from a source
math         = theorem/conjecture/definition/skeleton
null_case    = pre-registered kill condition
test         = computable or argumentative test
colab        = notebook specification
finding      = result of a test
collision    = contradiction / semantic collision
request      = file or data request for Den
verdict      = survived / dead / demoted / frozen / promoted
index        = run table of contents
```

---

## 5. Status lifecycle

```text
spark
  ↓
quarantine
  ↓
source_audit
  ↓
math_skeleton
  ↓
runnable
  ↓
run_done
  ↓
survived / demoted / dead / frozen / promoted
```

### Meaning of statuses

- **spark:** interesting, not trusted.
- **quarantine:** too broad / too charismatic / explains too much.
- **source_audit:** needs primary sources.
- **math_skeleton:** needs exact theorem/conjecture statement.
- **runnable:** has a test spec.
- **run_done:** notebook or argument executed.
- **survived:** passed its current NULL-case.
- **demoted:** useful as metaphor, education, or visualization, not load-bearing.
- **dead:** killed by NULL/source/math/test.
- **frozen:** not now; return later.
- **promoted:** ready for DIG node / report / notebook.

---

## 6. Claim strength fields

### 6.1 `claim_type`

```text
theorem
conjecture
empirical
interpretation
method
metaphor
protocol
request
```

### 6.2 T-scale

For speculation only:

```text
T1 = theorem-grade anchor
T2 = strong formal/experimental anchor
T3 = disciplined hypothesis
T4 = speculative bridge
T5 = fringe magnet / dangerous universal solvent
```

### 6.3 GRADE

For empirical claims only:

```text
high
moderate
low
unknown
```

Never convert T-rating into GRADE.  
Never convert elegance into evidence.

---

## 7. Required `this_is_not` patterns

Every block must actively block at least one overclaim.

Examples:

```json
"this_is_not": [
  "This is not a proof that reality is literally an interference pattern.",
  "This is not evidence for a recoverable original source.",
  "This is not a novelty claim before source audit.",
  "This is not a claim about qualia.",
  "This is not a replacement for the established theorem; it is an interpretive lens over it."
]
```

If `this_is_not` is empty, the block is invalid.

---

## 8. Null-first rule

Before a claim can become exciting, it must specify what would kill or demote it.

Null-case block:

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "null_case",
  "block_id": "M-RUN-0002-014",
  "claim_target": "M-RUN-0002-003",
  "title": "Pair-correlation kernel null",
  "kill_condition": "After accepted unfolding and finite-size controls, the zero pair-correlation fails to fit the sine-kernel form within expected error.",
  "demote_condition": "The fit works numerically, but the diffraction interpretation adds no predictive constraint.",
  "this_is_not": [
    "This is not a post-hoc explanation after seeing the plot."
  ],
  "status": "pre_registered"
}
```

---

## 9. Source audit block

Every paper enters as a source block, then evidence blocks are extracted from it.

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "source",
  "block_id": "M-RUN-0003-021",
  "title": "Montgomery pair correlation source",
  "bibliographic_status": "needed",
  "source_type": "primary_paper",
  "identifier": {
    "doi": null,
    "arxiv": null,
    "url": null,
    "citation_string": "exact citation pending"
  },
  "needed_for": ["M-RUN-0002-003"],
  "what_it_must_support": [
    "Exact pair correlation statement and hypotheses.",
    "Whether sine-kernel form is theorem/conjecture/numerical evidence."
  ],
  "this_is_not": [
    "This is not accepted as support until opened and extracted."
  ],
  "requested_from_Den": true,
  "priority": "high"
}
```

---

## 10. Math skeleton block

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "math",
  "block_id": "M-RUN-0004-008",
  "title": "Theorem/conjecture skeleton",
  "math_kind": "conjecture",
  "formal_statement": "Exact statement goes here.",
  "hypotheses": [],
  "conclusion": [],
  "what_it_does_not_say": [],
  "used_by_claims": [],
  "this_is_not": [
    "This is not a proof sketch unless proof_status says proven."
  ],
  "proof_status": "unknown",
  "references": []
}
```

The point of math skeletons: anomalies often hide in hypotheses, not conclusions.

---

## 11. Test / Colab block

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "colab",
  "block_id": "M-RUN-0005-002",
  "title": "R14-A zeta kernel notebook",
  "notebook_name": "R14_A_zeta_kernel.ipynb",
  "target_claims": ["M-RUN-0002-003"],
  "inputs_needed": [
    "table of Riemann zeta zeros",
    "unfolding method reference"
  ],
  "libraries": ["numpy", "scipy", "matplotlib", "mpmath"],
  "fixed_seed_required": true,
  "steps": [
    "load zeros",
    "unfold spacings",
    "estimate pair-correlation",
    "overlay sine-kernel baseline",
    "compute residuals",
    "write FINDINGS <= 10 lines"
  ],
  "null_case": "Kernel does not fit after standard controls.",
  "this_is_not": [
    "This notebook is not a proof of the Riemann hypothesis.",
    "This notebook is not a proof of interference ontology."
  ],
  "output_files": ["FINDINGS_R14_A.md", "fig_R14_A_kernel.png"]
}
```

---

## 12. Request block for Den

This is how agents ask Den for files from scientific libraries.

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "request",
  "block_id": "M-RUN-0003-050",
  "title": "Need primary source for zeta pair correlation",
  "priority": "high",
  "needed_for": ["R14-A", "M-RUN-0002-003"],
  "requested_item": {
    "exact_title": "pending",
    "authors": ["Montgomery"],
    "year": "1970s",
    "doi_or_arxiv": null,
    "acceptable_substitute": "A modern survey that quotes the exact pair-correlation conjecture with references."
  },
  "why_needed": "To separate theorem, conjecture, and numerical evidence before writing MATH_R14_A.md.",
  "this_is_not": [
    "This is not a request for blog summaries or encyclopedia pages."
  ],
  "status": "requested"
}
```

---

## 13. Collision handling

Contradictions are not garbage. They are collision events.

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "collision",
  "block_id": "M-RUN-0006-009",
  "title": "Diffraction metaphor overclaim collision",
  "blocks_in_conflict": ["M-RUN-0002-003", "M-RUN-0004-008"],
  "collision_type": "overclaim",
  "description": "Mathematical source supports sine-kernel statistics; it does not support literal physical diffraction ontology.",
  "resolution_options": [
    "demote ontology claim to metaphor",
    "keep computable visualization as educational",
    "ask for a stronger source if load-bearing use is desired"
  ],
  "this_is_not": [
    "This is not a deletion of the idea; it is a boundary marker."
  ],
  "status": "open"
}
```

---

## 14. Verdict block

```json
{
  "schema": "ompu.mblock.v0.1",
  "block_kind": "verdict",
  "block_id": "M-RUN-0008-001",
  "title": "R14-A cycle-01 verdict",
  "target_blocks": [],
  "verdict": "demoted",
  "reason": "Numerical visualization survived, but ontological reading added no testable prediction.",
  "survives_as": [
    "educational notebook",
    "visual intuition for sine-kernel statistics"
  ],
  "dies_as": [
    "load-bearing claim that zeta zeros are literally a diffraction pattern"
  ],
  "next_step": "publish as DIG-2xx notebook only",
  "this_is_not": [
    "This is not a failure; demotion is a valid research outcome."
  ]
}
```

---

## 15. End-of-run JSON index

Every pass ends with a JSON file.

Filename:

```text
RUN-0001_TOC.json
```

Minimal structure:

```json
{
  "schema": "ompu.run_index.v0.1",
  "run_id": "RUN-0001",
  "date": "2026-07-07",
  "router": "Den",
  "assembler": "Neo",
  "input_summary": "Methodology request: JSON/M-blocks with this_is_not, linear routing, file collection.",
  "outputs": [
    {
      "file": "DIG-001_Methodology_MBlocks_v0_1.md",
      "kind": "methodology",
      "status": "created"
    },
    {
      "file": "MBLOCK_SCHEMA_v0_1.json",
      "kind": "schema",
      "status": "created"
    }
  ],
  "toc": [
    {
      "section": "0",
      "title": "Core rule"
    }
  ],
  "next_agent_prompt": {
    "target": "Phi",
    "purpose": "Return a cold claim ledger for next step."
  },
  "open_requests": [],
  "next_run_expected": "RUN-0002"
}
```

---

## 16. Routing rules

Den routes linearly because Den is the narrow physical bus.

```text
Agent produces packet → Den brings packet → Neo parses/links → next packet request → Den routes.
```

No agent assumes access to background state outside the packet.

Every packet must include:

```text
run_id
what changed
new blocks
killed/demoted blocks
requested files
next suggested move
```

---

## 17. WIP discipline

Active lanes:

```text
max_active_research_cards = 3
max_active_colabs = 2
max_active_syntheses = 1
```

Everything else goes to `frozen`.

Recommended current active lanes:

```text
R12 = home specimen / graph percolation
R14-A = zeta pair-correlation kernel, if accepted as new synthesis probe
R14-C = caustic alphabet, after R14-A source audit starts
```

Do not activate all R14 supports at once. The fish has too many glowing teeth.

---

## 18. Promotion rules

A block can become load-bearing only if:

1. `this_is_not` is populated.
2. `source_status` is not `agent_claim_unverified`.
3. There is a NULL-case.
4. The theorem/conjecture/empirical status is separated.
5. A second architecture has reviewed it blindly, or the lack of second review is disclosed.
6. It survived or was honestly demoted.

A block can become a DIG node only if:

```text
source audit done
math skeleton done where applicable
notebook or argument test done where applicable
verdict pack written
Zenodo graph relation selected
```

---

## 19. Publication routing

```text
methodology       → DIG-001
field atlas       → DIG-003
workstream report → DIG-1xx
notebook/finding  → DIG-2xx
synthesis         → DIG-3xx
novelty candidate → DIG-4xx
dead hypothesis   → DIG-9xx
```

Negative results are not hidden. They are graph mass.

---

## 20. Φ / other-agent packet requirements

When another model returns a pass, ask for:

```text
1. Atomic claims as JSON/M-blocks.
2. Each block has this_is_not.
3. Each claim has type: theorem/conjecture/empirical/interpretation/metaphor.
4. Every empirical claim has GRADE or unknown.
5. Every speculative bridge has T-rating.
6. Each claim names exact primary sources needed.
7. Each claim has a cheap kill/demotion test.
8. Requested files are explicit and library-friendly.
9. The pass ends with RUN-XXXX_TOC.json.
10. The agent proposes exactly one next step, not ten.
```

---

## 21. Operating sentence

> We are not collecting beautiful explanations.  
> We are collecting small testable blocks with explicit anti-overclaim membranes.

Or in field manual dialect:

> Копай где фонит. Но каждый светляк получает бирку, дозиметр и `this_is_not`.

