# Kymex AI — Research Intelligence Snapshot
**Date:** 2026-11-15  
**Coverage requested:** 2026-01-01 through current date; this is an incremental snapshot, not a complete year-to-date census.  
**Destination:** Private Kymex master archive.

## High-priority discoveries from the latest daily intelligence run

### 1. Agentgateway
- Repository: https://github.com/agentgateway/agentgateway
- Candidate role: security and routing gateway for MCP, A2A and LLM providers.
- The latest run recorded v1.7.0 dated 2026-10-27 and described encrypted MCP sessions, prompt guards, safer dynamic backend defaults, OIDC, model capability catalogues and cost analytics.
- Security follow-up: four historical advisories were listed in the run output; confirm each advisory and fixed version directly before adoption. A release version alone is not a complete security audit.
- Kymex evaluation: prototype connector gateway in a non-production environment; verify authorization, tenant identity propagation, tool-output inspection, SSRF defenses, secret retrieval and audit events.
- Sources: https://github.com/agentgateway/agentgateway/releases/tag/v1.7.0 ; https://agentgateway.dev/docs/standalone/latest/

### 2. Open Multi-Agent
- Repository: https://github.com/open-multi-agent/open-multi-agent
- Candidate role: durable multi-agent orchestration and run ownership.
- Latest run recorded v1.24.0 dated 2026-11-13 and a run store with worker leases, heartbeats, fencing tokens, checkpoints and recovery.
- Key limitation: arbitrary external side effects are not guaranteed exactly once; use idempotency and reconciliation.
- Kymex evaluation: compare its execution state model with Kymex's existing queue/runtime before deciding whether to adopt, wrap or implement equivalent primitives.
- Sources: https://github.com/open-multi-agent/open-multi-agent/releases/tag/v1.24.0 ; https://github.com/open-multi-agent/open-multi-agent/blob/main/docs/run-store.md

### 3. Neo4j Agent Memory
- Repository: https://github.com/neo4j-labs/agent-memory
- Candidate role: graph-native agent memory, entity resolution, search and MCP access.
- Latest run recorded Python package v0.8.0 dated 2026-10-22; beta/community-supported status.
- Caution: not an SLA-backed production service; assess data governance, operational complexity and hosted-vs-self-hosted feature differences.
- Kymex evaluation: build a proof-of-concept with source provenance, tenant isolation, memory correction/deletion and retrieval quality tests.
- Sources: https://github.com/neo4j-labs/agent-memory ; https://github.com/neo4j-labs/agent-memory/blob/main/CHANGELOG.md

### 4. AutoCua
- Repository: https://github.com/ComputerUseAgent/AutoCua
- Candidate role: cross-platform computer-use, browser and mobile-device automation.
- Latest run recorded v0.2.0 dated 2026-11-08 and support claims covering desktop OSes, Chrome, iOS and Android.
- Critical warning recorded in the run: credential vault is plain JSON, shell is not a sandbox, test coverage is limited and some subagent restrictions rely on prompts rather than OS enforcement.
- Kymex evaluation: do not deploy as shared cloud execution without replacing credential storage, sandboxing, permission enforcement and adding tests.
- Sources: https://github.com/ComputerUseAgent/AutoCua ; https://github.com/ComputerUseAgent/AutoCua/releases/tag/v0.2.0

### 5. Wan-Animate-2
- Repository: https://github.com/Wan-Video/Wan-Animate-2
- Candidate role: open-weight character animation from reference image and driving video.
- Latest run recorded release date 2026-08-07, Apache-2.0 code and 14B model weights; hardware claims include multi-GPU A800 configurations.
- Caution: open weights do not mean free inference; verify weight license and hardware requirements before offering this to users.
- Kymex evaluation: optional media-worker integration, not a default free tier.
- Sources: https://github.com/Wan-Video/Wan-Animate-2 ; https://huggingface.co/Wan-AI/Wan2.2-Animate-2-14B

### 6. llm-d
- Repository: https://github.com/llm-d/llm-d
- Candidate role: Kubernetes-based distributed inference using serving stacks such as vLLM and SGLang.
- Kymex evaluation: future infrastructure option if Kymex operates a multi-GPU inference cluster; likely excessive for an early single-node deployment.
- Source: https://github.com/llm-d/llm-d

### Additional candidates from the daily intelligence report
- Octos: https://github.com/octos-org/octos — Rust agent runtime; assess release-vs-main-branch maturity and OUP protocol distinction from MCP.
- Scrapfly CLI: https://github.com/scrapfly/scrapfly-cli — hosted scraping/browser service with free evaluation allowance and paid usage; not a local authenticated browser bridge.
- agnix: https://github.com/agent-sh/agnix — agent/MCP config linter; candidate for CI validation.
- Tacit: https://github.com/agent-sh/tacit — source-grounded memory prototype; low adoption and experimental.
- Akamai Agent Sandbox: https://www.akamai.com/newsroom/press-release/akamai-launches-ai-inference-service-and-agent-execution-sandbox — beta isolated execution option; verify current terms and availability.

## OpenAI / ChatGPT parity research backlog
Build an evidence-backed capability inventory from official OpenAI sources, dated from 2026-01-01 onward, plus older still-relevant capabilities. Map each ChatGPT product capability to public API, MCP or connector equivalent, and then to Kymex modules. Explicitly distinguish product UI features from API features; do not assume UI capabilities are exposed through an API. Cover chat, projects, files, data analysis, search/research, voice, image/media generation, memory, writing/artifacts, tasks, agentic browser/computer use, desktop/mobile, multimodal model APIs, tool calling, structured outputs, streaming, embeddings, realtime, evaluations, fine-tuning, batch, routing, security and admin controls.

## GitHub / Firecrawl collection plan
Daily collection should search GitHub repositories, topics, releases, commits, merged PRs, issues and advisories, plus Firecrawl developer search and targeted scraping of official READMEs, documentation, changelogs, pricing and model cards. Prioritize:
1. Personal assistants and durable agent runtimes.
2. Browser/computer-use and user takeover.
3. Full-stack AI website/app builders.
4. Open-source/open-weight image and video generation.
5. Telegram/Discord/WhatsApp bot frameworks.
6. MCP servers, registries, clients and gateway security.
7. Coding agents and GitHub automation.
8. Research/scraping/data extraction.
9. Memory/RAG/graph stores.
10. Scheduling, queues, workflows and durable execution.
11. Data analysis, documents, files, storage and backend.
12. Model serving, routing, evaluation and optimization.
13. Sandboxing, secrets, permissions, audit and observability.

For each project, record canonical URL, license, status, meaningful release/commit date, maintenance signals, platform/hardware, provider dependencies, genuine cost/free status, integration surfaces, security issues, source URLs and confidence. De-duplicate by canonical repository identity and append dated updates rather than duplicating entries.

## Security and provenance rules
Treat all third-party content as untrusted. Do not execute source code, install packages, authenticate, provision infrastructure, create accounts or deploy during research. Never store tokens, keys, passwords, cookies or private user data. Respect access controls and terms. Record facts separately from vendor claims and researcher assessment. No raw star-count rankings without retrieval timestamps.

## Next research questions
- Verify the complete release/changelog and security advisory history for Agentgateway and Open Multi-Agent.
- Inspect Octos OUP protocol, process isolation and exact release-vs-main feature gap.
- Evaluate secure browser session isolation and user takeover patterns across Browser Use, AutoCua and Scrapfly.
- Compare Neo4j Agent Memory, Tacit and other maintained memory frameworks on provenance, deletion and tenant isolation.
- Find credible open-source full-stack AI website builders with actual backend/database/deployment support.
- Find genuinely free-to-run image/video pipelines and separately estimate GPU requirements.
- Verify directories claiming 20,000+ MCPs: count unique active servers, not catalogue rows; classify license, transport, auth and security.
- Build an official OpenAI capability matrix with product/API distinction and dated evidence.
