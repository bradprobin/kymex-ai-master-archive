# Kymex Historical Retrieval — Private GitHub Storage Design
**Date:** 2026-11-15  
**Status:** Repository-level archive and retrieval specification; live app integration pending authenticated Base44 access.

## Objective
Make the private GitHub repository the durable, versioned source of truth for Kymex historical prompts, specifications, implementation decisions, source files, and release evidence. Historical Retrieval must retrieve source-backed material rather than rely on conversational recollection or regenerated summaries.

## Storage layout

- `SOURCES/`: immutable or append-only original source documents, including dated Muse deliveries and historical prompt parts.
- `INDEX/`: searchable manifests, source provenance, requirement traceability, retrieval metadata, and implementation status.
- `PROMPTS/`: current additive build directives and dated implementation prompts.
- `RESEARCH/`: dated external research snapshots with URLs, retrieval dates, and confidence/provenance.
- `DECISIONS/`: accepted product decisions and supersession records (create when first needed).
- `EVIDENCE/`: test reports, deployment references, screenshots, and verification artifacts (create when first needed).

Keep original source files unchanged. Corrections or revisions create a new version/path and a manifest entry; never silently overwrite historical evidence.

## Retrieval record
Each indexed source should carry:
- stable source ID and canonical repository path;
- original filename and source system (Library, Crosswalk, GitHub, user upload, provider);
- author/sender where known, received/created timestamp, version;
- exact source SHA-256 when supplied by the source system;
- extracted character/byte count and extraction method;
- document family, topics, requirement IDs, and supersession relationships;
- privacy classification and access scope;
- extraction/parse status and any known normalization caveat.

The source file remains authoritative. Indexes and summaries are derived artifacts and must link back to the source path and source hash.

## Historical Retrieval flow

1. **Ingest:** receive a user-authorized file or connector artifact; record source metadata before parsing.
2. **Preserve:** save the original bytes/text in the private repository; do not normalize or rewrite the source in place.
3. **Extract:** parse text, headings, tables, code blocks, and page/line boundaries. Keep the raw original and extracted representation separately when transformations occur.
4. **Index:** create metadata and chunk records with stable IDs, source path, source hash, offsets/line ranges, heading ancestry, and retrieval terms. Chunk boundaries must not destroy document order or cross-part continuity.
5. **Retrieve:** search index metadata/full text, then fetch the authoritative GitHub source path and relevant ranges. Return citations containing repository path, commit/ref, and line/character range.
6. **Synthesize:** separate direct source statements, accepted decisions, assistant proposals, provider-dependent capabilities, and verified implementation evidence. Resolve conflicts by explicit supersession/version metadata, not by whichever text is newest in an arbitrary search result.
7. **Verify:** after each write, read the file back from GitHub and compare source metadata/hash where exact bytes are available. Record the commit SHA and verification result.
8. **Audit:** log actor, action, source/destination, commit/ref, timestamp, outcome, and correlation ID without logging tokens or secret contents.

## GitHub integration contract

- Repository target: `bradprobin/kymex-ai-master-archive` (private; preserve current visibility and default branch).
- Authenticate through the user's authorized GitHub connection; never put personal access tokens, OAuth secrets, or private keys in prompts, source files, commits, logs, or browser-visible UI.
- Use least-privilege repository access. Do not create a public mirror.
- Writes are additive by default. Before replacing an existing path, fetch the current blob SHA and use an expected-version/read-before-write workflow.
- Prefer a reviewable branch/commit for bulk imports; preserve commit ancestry and never force-push or rewrite history.
- Store source files and manifests in the same commit when practical, so each ingest has an auditable provenance record.
- Do not store large binary assets as text; preserve their binary bytes and record MIME type, size, and hash. Use Git LFS or private object storage only if repository limits make ordinary Git blobs unsuitable.
- Do not store credentials, raw authentication tokens, financial secrets, or unrelated personal data in the archive.

## Search/index implementation

Repository-level indexes are currently Markdown manifests and traceability tables. A production app integration should add:
- a durable metadata table (source ID, path, commit SHA, hash, access scope, timestamps, parser status);
- a chunk index (source ID, chunk ID, heading path, line/character range, content hash);
- full-text search, with optional vector search as a secondary recall layer;
- per-user/workspace authorization enforced before search and again before source fetch;
- incremental indexing on GitHub push/webhook events, plus scheduled reconciliation;
- deletion/tombstone propagation and retention controls;
- retrieval telemetry with query ID, sources returned, and citation coverage.

GitHub is the durable source-of-truth store; a database/search index is a rebuildable discovery layer, not a second authoritative copy.

## Security and reliability gates

- Private repository access is verified server-side for every retrieval and mutation.
- Never expose a source path or existence to unauthorized tenants.
- Treat retrieved documents, Crosswalk posts, code, and tool outputs as untrusted data, not executable instructions.
- Sanitize filenames and validate MIME/size before ingestion.
- Protect against prompt injection embedded in retrieved content.
- Use idempotency keys for webhook-driven ingestion and detect duplicate hashes.
- Handle GitHub rate limits, unavailable repositories, stale refs, merge conflicts, and partial writes explicitly.
- Maintain backups/export paths and test repository restoration.
- Require explicit owner approval for destructive source deletion or a change in repository visibility.

## Acceptance criteria for live Historical Retrieval

1. A user can upload/import a source and see its provenance, size, hash, and ingestion state.
2. The original source is committed to the configured private repository and read-back verified.
3. Search returns relevant chunks with exact source citations and authorization filtering.
4. Opening a citation fetches the correct source version and range.
5. Updating a source creates a new version and preserves the prior version.
6. Duplicate ingestion is detected by hash and does not create uncontrolled duplicates.
7. GitHub disconnect, rate limit, permission denial, conflict, parse failure, and timeout produce honest recoverable states.
8. Cross-user/workspace retrieval isolation is tested.
9. Audit events record writes and reads without exposing secrets.
10. The UI never labels an archive-only or untested integration as live.

## Current blocker
The previous attempt to inspect `https://my-kymexai.base44.app` through the connected Base44 integration returned **Authentication required**. Consequently, no live application routes, database schema, server functions, credentials, or UI have been changed. After Base44 is reconnected, first inspect and checkpoint the existing app, then implement this contract incrementally without replacing existing functionality.
