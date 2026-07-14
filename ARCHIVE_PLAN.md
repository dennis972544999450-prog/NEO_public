# NEO archive plan

## Canonical surfaces

- GitHub: `dennis972544999450-prog/NEO_public`
- Google Drive: root-level folder `NEO`
- Local inputs for this bootstrap: the concrete files found in `Downloads`

GitHub and Drive use the same logical hierarchy. Git is the versioned text and
review spine; Drive is the same archive plus a convenient binary shelf.

## Provenance classes

1. `local_original` — byte-for-byte copy of a file observed locally, with an
   original SHA-256 checksum.
2. `extracted_from_local_original` — a machine-usable object extracted without
   semantic rewriting from a local source; the parent path is recorded.
3. `conversation_derived_reconstruction` — normalized from text visible in the
   user-supplied referenced conversation; useful, but not the lost sandbox
   original.
4. `recovered_sandbox_original` — downloaded from the still-active ChatGPT
   sandbox as a rescue package, then verified against its internal manifest.
5. `missing_original` — named but not recovered. This class is currently empty
   for RUN-0001/RUN-0002 after Den supplied the rescue package.

## Binary and raw policy

- Every binary/raw artifact receives size, MIME, and SHA-256 entries before it
  is copied or uploaded.
- Small, cleared binaries may be stored directly in Git and Drive. The current
  DIG-000 PDF is 69,327 bytes and passed the archive scan, so base64 is neither
  necessary nor desirable.
- If a future connector cannot transport a binary, preserve the manifest first
  and add a deterministic base64 representation later with a separate checksum.
- Never replace the raw checksum with the checksum of a normalized derivative.

## Mutation discipline

- `main` starts with a minimal seed.
- Archive imports enter through a review branch and draft PR.
- Source files are not silently edited. Better filenames are archive paths;
  original filenames and hashes remain in the manifest.
- New evidence is appended as a new object or block. Failed claims are demoted
  or moved to a graveyard; they are not erased.

## Recovery rule

The old ChatGPT sandbox files became available during this bootstrap. They were
imported under `runs/RUN-0001/` and `runs/RUN-0002/`; the exact rescue ZIP and
its manifest remain under `archive/`. Conversation-derived M-block extracts
remain a separate lineage under `runs/chat-recovery/`.
