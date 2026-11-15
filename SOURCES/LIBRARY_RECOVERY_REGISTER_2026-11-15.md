# Kymex Library Recovery Register — 2026-11-15

## Purpose and scope
Inventory of Kymex AI source prompts, implementation plans, documentation and visual assets recovered from the user's ChatGPT Library. This register distinguishes canonical source artifacts from duplicate versions, derivative compilations, and visual references. It does not imply that the destination application has been implemented.

## Canonical historical compilation
- **Name:** Kymex_AI_Complete_Historical_Migration_Master_September_to_November_12_2026.txt
- **Library file ID:** file_00000000a04081f4beec6305632c7d12
- **Size:** 3,338,619 bytes
- **Decoded characters:** 3,328,893
- **Lines:** 54,932
- **SHA-256:** 78b39b256ee355655b40a5b24dbf8fb85c2086e05f1abb4e7e50f55b62f11c01
- **Library created:** 2026-11-12
- **Coverage stated by source:** September 2026 through November 12, 2026
- **Scope:** combines the September verified prompt archive, unique material from the smaller September archive, the Beyond Chat plan, recovered November 2 Muse + ChatGPT requirements, November 3 agent/browser/MCP/creative-studio requirements, and four November 12 implementation prompts.
- **Provenance caveat:** the historical source itself says the original Muse-authored Crosswalk post was not retrieved; reconstructed requirements are not a verbatim quote of that post.

## Primary source files recovered
| Source | Library file ID | Bytes | Decoded characters | Lines | SHA-256 | Relationship |
|---|---|---:|---:|---:|---|---|
| Historical Migration Master (Sep–Nov 12) | file_00000000a04081f4beec6305632c7d12 | 3,338,619 | 3,328,893 | 54,932 | 78b39b256ee355655b40a5b24dbf8fb85c2086e05f1abb4e7e50f55b62f11c01 | Cumulative historical compilation |
| Unified Prompt — 2M Verified | file_00000000b93c81f48c8b7b33f9589362 | 2,634,435 | 2,629,045 | 43,915 | 2bf0e330b161930999b713335aeeda57da1df4272c2a0dc826b42cebace0a550 | Primary September base embedded in cumulative master |
| Earlier Unified Prompt | file_00000000f8e081f498aee156d0913604 | 1,761,899 | 1,752,967 | 30,925 | f34ac11d09cf6fd0e39466e8faa6473e8e32478de5e06b5b4d51a2d8a320b1d2 | Overlapping predecessor; unique paragraphs were reconciled into cumulative master |
| Complete Documentation Package | file_00000000c4548211aff78ffb0f4fa7ee | 90,849 | 89,718 | 3,876 | 1fdbd456bdb9394bc7eeca811518582618d63e2b1a9d86ba0afe10fb5507affa | Documentation package; assess overlap before treating as unique |
| Beyond Chat Modification Plan | file_00000000ba5081f4aa38a8bddb3d4a34 | 52,158 | 51,836 | 1,154 | c3628f4bc19d90b1c50120bf6292efb811415cd215be9812f75f500e468b0ad4 | Separate modification plan, also reconciled into cumulative master |

The raw character total of the five files above is **7,852,459 characters**, but this is not a unique-content count: the 3.33 MB cumulative master already incorporates the verified base and reconciled unique portions from earlier sources. Do not add overlapping versions together and describe the result as unique requirements.

## Additional Kymex-related Library assets identified
- `AI_Agent_Platform_Complete_Prompt_Updated-1.txt` — 46,809 bytes; Library file ID `file_00000000f38881f8942c9b65d64ec2ae`. General AI-agent platform build prompt used as Kymex source material; begins with the production-ready mobile-first agent platform definition.
- `KYMEX-AI-COMPLETE-DOCUMENTATION(1).txt` — 90,849 bytes; Library file ID `file_0000000011508243b6fce1cf6d08caa9`. Later duplicate upload of the documentation package; do not count as new content without a content comparison.
- Kymex visual assets:
  - `Streamline K Geometric Logo.png` — `file_000000008d6c81f498d77f34182bb5d9`
  - `Dynamic Segmented K Logo.png` — `file_000000002f98820ab28f75272bb115de`
  - `Dynamic Segmented K Logo(1).png` — `file_000000003fdc821092663830e0f4d025`
  - `Dynamic K Speedmark Logo.png` — `file_000000000cc48246bb65412870040470`
  - `Futuristic K Speed Emblem.png` — `file_00000000e0ac81f4b3fd570d975331bb`
  - `Dynamic Gradient K Emblem.png` — `file_00000000ef5082439c209d39598bce5e`
  - `Kymex AI: Infinite Creative Possibilities.png` — `file_000000002bc082109b988977a5d71fac`
- The visual assets remain in Library; this run did not upload binary assets into GitHub.

## Related but separate projects
Wroan AI video-generator prompts, DocuForge AI document-generator prompts, MoniePay PSB specifications, and Keme fiction/media prompts are separate project artifacts. Do not silently merge their full specifications into Kymex. Kymex may integrate compatible capabilities through provider adapters only when the user has requested that relationship and the provider's real interface, terms and cost have been verified.

## GitHub transfer status
The 3.33 MB historical master was extracted into four GitHub source parts:
- `SOURCES/HISTORICAL_MASTER_2026-11-12_PART_001_OF_004.txt`
- `SOURCES/HISTORICAL_MASTER_2026-11-12_PART_002_OF_004.txt`
- `SOURCES/HISTORICAL_MASTER_2026-11-12_PART_003_OF_004.txt`
- `SOURCES/HISTORICAL_MASTER_2026-11-12_PART_004_OF_004.txt`

The four part blobs were committed together on `main` in commit `b2aeebadb886027e5ab5077ddb323fcb3ce714bd`. Their extracted text totals 3,328,907 characters, which is 14 characters more than the Library-decoded source count. This extraction discrepancy means the GitHub parts must **not** be labelled a byte-for-byte or hash-identical copy. The exact canonical Library original remains intact with the SHA-256 above. The split GitHub copy preserves the retrieved line ranges but requires a later exact-normalization comparison before any claim of verbatim identity.

The 2.63 MB and 1.76 MB predecessor files are represented within the cumulative historical compilation; their separate original Library artifacts remain available by the IDs above. The 90 KB documentation package and 46 KB agent platform prompt are identified but not yet transferred as separate verbatim GitHub files.

## Application implementation status
- Intended destination: https://my-kymexai.base44.app
- Historical reference only: https://the-kymex-ai.base44.app
- GitHub repository: https://github.com/bradprobin/kymex-ai-master-archive (private, branch main)
- Base44 connection attempt on 2026-11-15 returned **Authentication required** before app listing or inspection. No Base44 app code, schema, data, integrations or settings were modified in this run.
- Consequently, all feature implementation statuses remain **not audited / unknown** until Base44 access is restored and the target app is inspected.

## Next recovery steps
1. Compare the GitHub split extraction against the Library original and correct the 14-character discrepancy before calling it exact.
2. Transfer the standalone 90 KB documentation package and 46 KB AI Agent Platform prompt as separate source artifacts, preserving source IDs and hashes.
3. Inventory later Kymex-related Library files and screenshots, with duplicates identified by hash.
4. Reconnect Base44, inspect the correct destination app, create a restorable checkpoint, and produce a route/entity/function/integration audit before code changes.
5. Build a requirement-to-implementation traceability matrix and implement missing features in migration-safe batches.

## Additional standalone source records committed
- `Kymex_AI_Joint_Master_Build_Prompt.txt` — Library file ID `file_00000000a080820eae5f60cebff84450`, 24,210 bytes, dated 2026-11-02. Committed as `SOURCES/KYMEX_JOINT_MUSE_CHATGPT_MASTER_PROMPT_2026-11-02.txt`. This is the recovered joint Muse AI + ChatGPT implementation prompt; the source archive explicitly warns that the original Muse-authored Crosswalk post itself was unavailable.
- `Kymex_AI_Archive_Manifest.txt` — Library file ID `file_00000000381481f4ad5ba42936c0b6e0`, 700 bytes, dated 2026-11-12. Committed as `SOURCES/KYMEX_HISTORICAL_ARCHIVE_MANIFEST_2026-11-12.txt`. It records the compilation provenance and unique-paragraph counts.
