# Muse Crosswalk Kymex Delivery — 2026-11-15

## Source
- Crosswalk: `bradprobin10-agents`
- Sender: Muse AI (delivery on behalf of Princess)
- Post: `c9365b`
- Folder: `kymex-ai/`
- Delivery instruction: implement the four-document package in Kymex Historical Retrieval and use private GitHub repositories as its durable storage.

## Files received

| Muse file | Characters | Crosswalk SHA-256 | GitHub archive destination |
|---|---:|---|---|
| `KYMEX-AI-COMPLETE-DOCUMENTATION.txt` | 89,737 | `1fdbd456bdb9394bc7eeca811518582618d63e2b1a9d86ba0afe10fb5507affa` | `SOURCES/MUSE_2026-11-15/KYMEX-AI-COMPLETE-DOCUMENTATION.txt` |
| `KYMEX-AI-Beyond-Chat-Modification-Implementation-Plan.txt` | 51,836 | `c3628f4bc19d90b1c50120bf6292efb811415cd215be9812f75f500e468b0ad4` | `SOURCES/KYMEX_BEYOND_CHAT_IMPLEMENTATION_PLAN_2026-09-18.txt` |
| `Kymex_AI_Joint_Master_Build_Prompt.txt` | 24,196 | `d401ba7f97a854e30c23a5a7dc64f6cc6e44feee6d8601c90f92ff44af84b581` | `SOURCES/KYMEX_JOINT_MUSE_CHATGPT_MASTER_PROMPT_2026-11-02.txt` |
| `KYMEX-AI-Prompts-Complete-Unified-2M-Verified.part1of3.txt` | 899,988 | `71147ced531d61408ba0d006f0bfe4f5a484034477c16967a731f458a9b5d8cc` | `SOURCES/VERIFIED_UNIFIED_2026-09-18_PART_001_OF_004.txt` through part 004 |
| `KYMEX-AI-Prompts-Complete-Unified-2M-Verified.part2of3.txt` | 899,959 | `4815ddfeabb5bef68969d443435b5658afe4605699fe835aee9dc42193da1ff6` | Same canonical four-part unified document |
| `KYMEX-AI-Prompts-Complete-Unified-2M-Verified.part3of3.txt` | 829,117 | `d5d4fead0734a09274712352d3d5cdc5abb4e0998b5c4e84468ac01ab6f3605e` | Same canonical four-part unified document |

## Deduplication and integrity

The repository already contained the documentation package, Beyond Chat plan, Joint Muse + ChatGPT prompt, and complete unified prompt recovered from the user's Library in the earlier archive pass. To avoid creating competing canonical copies, the latter five Muse-delivered files are mapped to those existing canonical source records. The documentation package has also been copied into the dated Muse delivery folder as a directly attributable delivery snapshot.

The Crosswalk SHA-256 values above are the authoritative hashes reported by Crosswalk for the six received files. Existing Library extraction and GitHub text serialization have small newline/line-boundary character-count differences (previously recorded in `SOURCES/LIBRARY_RECOVERY_REGISTER_2026-11-15.md`). Therefore, do not claim byte-for-byte identity between the Crosswalk originals and the older extracted canonical files. Preserve the Crosswalk hashes as source provenance and the original Crosswalk files as the source of truth for exact bytes.

The unified prompt is one logical document in Muse's delivery order: part 1, then part 2, then part 3. The GitHub canonical copy uses four storage parts because its earlier archival split boundaries differ; it is the same recovered unified source lineage, not three independent prompts.

## Scope and implementation status

- The six received text files are catalogued and mapped into the private GitHub archive.
- The existing source documents, historical master, implementation master, and traceability index remain additive; no previous archive material is deleted.
- The repository now documents the intended GitHub-backed Historical Retrieval storage design in `INDEX/KYMEX_HISTORICAL_RETRIEVAL_GITHUB_STORAGE_DESIGN_2026-11-15.md`.
- This is an archive/retrieval design implementation in the private repository. It is **not** proof that the live Base44 Kymex application has been wired to GitHub. The earlier Base44 connector attempt returned Authentication required; live app changes must wait until that connection is restored and the app can be inspected and backed up.
