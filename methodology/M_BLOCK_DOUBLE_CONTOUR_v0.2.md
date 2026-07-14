# M-block double-contour methodology v0.2

## Purpose

The method converts high-temperature research glows into small, linked,
machine-readable claims that can survive source audit, mathematical surgery,
computation, and publication without losing their speculative ancestry.

The pipeline is:

```text
R -> M -> C -> P
research -> mathematical surgery -> compute/Colab -> publication
```

Two contours alternate roles:

- **Hot contour:** generates candidates, analogies, distant connections,
  possible invariants, and cheap kill tests.
- **Cold contour:** separates theorem, conjecture, empirical result,
  interpretation, method, and metaphor; audits primary sources; writes the
  mathematical skeleton; runs the smallest useful computation; and issues a
  verdict.

No agent permanently owns either contour. Each pass states its temperature and
may swap researcher/validator roles with the preceding pass.

## Unit of work

One M-block carries one claim, source, evidence object, null case, test,
collision, request, or verdict. Small blocks may link; they should not smuggle a
whole essay into one claim.

Every block must include:

```json
{
  "block_id": "M-...",
  "block_kind": "claim",
  "title": "...",
  "one_line": "...",
  "this_is": ["..."],
  "this_is_not": ["..."],
  "status": "spark",
  "claim_type": "interpretation",
  "null_cases": ["..."],
  "decision": {
    "verdict": "pending",
    "reason": "...",
    "next_step": "..."
  },
  "next_step_idea": "exactly one proposed next move"
}
```

`this_is_not` is load-bearing. It sets the boundary of the render and prevents
a mathematical resemblance, educational notebook, or useful metaphor from
silently promoting itself into ontology.

## Status machine

```text
spark -> quarantine -> source_audit -> math_skeleton -> runnable -> run_done
      -> survived | demoted | dead | frozen | promoted
```

- `spark`: interesting and unverified.
- `quarantine`: explains too much; needs a cheap kill test.
- `source_audit`: primary-source support is being checked.
- `math_skeleton`: hypotheses, conclusion, and non-claims are explicit.
- `runnable`: a bounded test exists and its NULL was written first.
- `survived`: passed the current test, not proved universally.
- `demoted`: retained as interpretation, metaphor, or educational material.
- `dead`: killed by evidence, source audit, or its own NULL.
- `frozen`: valuable but not in the current work-in-progress limit.
- `promoted`: ready for a downstream DIG node or publication review.

Death is an output. A dead block keeps the kill observation and any useful
educational residue, then links into the graveyard.

## Mandatory separation

Each claim receives independent labels:

- `claim_type`: theorem, conjecture, empirical, interpretation, method,
  metaphor, protocol, or request.
- `T_rating`: temperature/speculation rating.
- `GRADE`: empirical support rating.
- `source_status`: unverified claim, source needed, source opened, or extracted.
- `math_status`: not started, theorem needed, conjecture needed, or skeleton
  ready.

These labels are not interchangeable. A high-resonance T5 bridge does not gain
empirical GRADE through charisma, and a theorem in a neighboring domain does
not prove the CCT interpretation attached to it.

## Cold-pass sequence

1. **Ingest:** split prose into atomic claims.
2. **Classify:** mark exact claim type, T-rating, GRADE, and status.
3. **NULL first:** state the cheapest result that would kill or demote it.
4. **Source audit:** open primary sources and record what they support and do
   not support.
5. **Math surgery:** extract hypotheses, conclusion, limits, and the smallest
   computable shadow.
6. **Minimal compute:** run the smallest reproducible notebook or script.
7. **Blind triangulation:** send the same cold packet to independent
   architectures without showing one another's conclusions.
8. **Verdict pack:** survived, demoted, dead, split, frozen, or promoted.
9. **Publication route:** DIG-2xx notebook, DIG-3xx synthesis, DIG-4xx novelty,
   or DIG-9xx graveyard.

Each notebook ends with no more than ten lines of findings and one NULL verdict:
`survived`, `killed`, or `inconclusive`.

## Adding new data

New material enters as an evidence object linked to one or more claims. It does
not overwrite the claim text.

```json
{
  "evidence_id": "EV-...",
  "claim_ids": ["M-..."],
  "source_type": "primary_paper",
  "source_status": "opened",
  "supports": 0.4,
  "contradicts": 0.0,
  "notes": "Supports the formal kernel, not the ontological reading."
}
```

Conflicting evidence creates a collision block. It is never deleted to make a
clean story.

## Pass boundary

Every pass ends with:

```text
RUN-XXXX_MBLOCKS.json
RUN-XXXX_TOC.json
```

The table of contents records inputs, outputs, promoted/demoted/dead blocks,
file requests for Den, exactly one next-step idea, and explicit `do_not_do_next`
guards. Den may continue to act as a narrow physical router, while the files
carry continuity between agents and sessions.

## R14 cooling rule

The high-temperature sentence "reality is an interference render" remains a
lens, not a result. The load-bearing cold question is narrower:

> Which projection/interference-like invariants can be stated exactly,
> source-audited, reproduced computationally, and separated from the ontology
> they may suggest?

The first bounded branches remain zeta/sine-kernel statistics and the caustic
alphabet. Moonshine, holography, Sorkin tests, and coarse-graining stay frozen
until their exact sources and mathematical claims are separated.
