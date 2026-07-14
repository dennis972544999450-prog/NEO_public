# Corpus safety and integrity review

Date: 2026-07-14

## Checks passed

- All Markdown, JSON, and JSONL inputs are strict UTF-8.
- All JSON and JSONL inputs parse.
- Every rescued sandbox file matches the SHA-256 value in its supplied
  manifest.
- The JSON and JSONL chat M-block forms contain the same four objects.
- RUN-0002 contains 23 unique block IDs; all blocks have the required M-block
  fields, including a non-empty `this_is_not` array.
- The two downloaded rescue ZIP aliases are byte-identical; only one is stored.
- Markdown fences in the local DIG corpus are balanced.
- No literal API credential, access token, private key, JWT, email address,
  phone number, or machine-local absolute path was found in the public corpus.

## Intentional public identity

The DIG-000 publication draft and Zenodo metadata include Den's publication
name and ORCID. This is retained as `public_identity`, not treated as a secret.

## Trust boundary

R01-R12 are model-generated literature maps. Archival integrity does not imply
source accuracy. They remain `unverified_agent_research` until each citation
and load-bearing claim passes source audit.

The rescued package states that its files were copied from the active ChatGPT
sandbox. The bytes and supplied internal manifest are verified; the provenance
statement itself remains user-supplied evidence.
