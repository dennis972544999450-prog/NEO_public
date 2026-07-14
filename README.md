# NEO_public

Public, provenance-first archive for NEO / OMPU research.

This bootstrap preserves the concrete local Anomaly Dig artifacts that were
present on Den's Mac on 2026-07-14. During the pass, Den recovered the missing
ChatGPT sandbox package; its internal hashes were verified before import.

## What is here

- `dig/DIG-000/` — the root research-program document and its PDF rendering.
- `research/dispatch/` — both dispatcher versions: R01-R12 and R01-R13.
- `research/literature_passes/` — the twelve separately generated R-card
  literature passes.
- `publication/zenodo/DIG-000/` — publication instructions and extracted
  Zenodo metadata.
- `methodology/` and `schemas/` — the recovered original M-block method/schema
  plus a new v0.2 continuity note.
- `runs/RUN-0001/` and `runs/RUN-0002/` — recovered original sandbox outputs.
- `runs/chat-recovery/` — M-blocks explicitly extracted from the referenced
  conversation, stored as JSON and JSONL.
- `archive/manifests/` — byte sizes, MIME types, source aliases, archive paths,
  and SHA-256 checksums.

## Trust labels

The R01-R12 files are archived as `unverified_agent_research`. They are useful
research maps, not source-audited publications. Citations and claims must pass
the cold contour before promotion.

Conversation-derived recovery files are marked as conversation extracts, not
the RUN-0001/RUN-0002 originals. The original sandbox package was downloaded
later in this pass, and its supplied per-file SHA-256 manifest matches every
imported file.

## Public-data boundary

The DIG-000 Markdown/PDF and Zenodo metadata contain the publication-intended
author name and ORCID. Automated scans found no literal credentials, private
keys, email addresses, phone numbers, JWTs, or machine-local absolute paths in
the archived source corpus. Token examples in the Zenodo instructions are
placeholders only.

The repository does not yet declare a repository-wide license. Individual
artifacts may contain their own publication metadata or licensing intent.

See [ARCHIVE_PLAN.md](ARCHIVE_PLAN.md) for the mirroring and recovery rules.
