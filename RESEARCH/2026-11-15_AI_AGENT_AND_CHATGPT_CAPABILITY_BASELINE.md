# Kymex AI — Research baseline
**Research date:** 2026-11-15  
**Status:** Initial desk research; not a hands-on benchmark.  
**Scope:** ChatGPT capability parity, agent ecosystem, MCP security, and Kymex implications.

## 1. ChatGPT capability map

OpenAI's public ChatGPT capability overview describes web search, deep research, image input/generation/editing, file and audio uploads, data analysis, voice, memory, projects, scheduled tasks, custom GPTs, and GPT Store. These are product capabilities; their exact availability depends on plan, region, workspace, rollout, and settings.

OpenAI's release notes describe ChatGPT Work as a multi-step agent experience for research, analysis, connected apps/files, and finished documents, spreadsheets, presentations, reports, and Sites. The same release notes describe scheduled tasks that can run once, recur, or monitor for changes. ChatGPT Work and Codex are distinct experiences: Work handles longer research and deliverables; Codex focuses on coding, debugging, tests, commands, code review, and repository work.

**Kymex implication:** Build a capability matrix that maps each product capability to a feasible Kymex implementation path. Do not assume ChatGPT UI features are exposed as OpenAI API endpoints. Verify API availability independently for every feature.

## 2. Open-source agent landscape — candidate shortlist

The sources reviewed surfaced several active ecosystem candidates:
- **Hermes Agent** — personal-agent runtime with persistent memory, skills, messaging channels, and scheduled work; inspect official repository, license, recent releases, and operational requirements before adoption.
- **nanobot** — lightweight personal-agent runtime with web UI, messaging, memory, MCP, and model routing; verify current upstream and feature maturity.
- **DeerFlow** — long-horizon agent harness with subagents, sandboxed execution, and memory; assess deployment complexity and fit.
- **OpenHands** — autonomous software-engineering agent; assess coding workflow and isolation model.
- **Browser Use** — browser automation library for agents; evaluate page-state reliability, session isolation, and human takeover.
- **Playwright MCP** — browser automation through MCP; review official Microsoft repository and tool permissions.
- **Goose** — MCP-oriented agent framework; compare extension model and local execution controls.
- **Cline** — coding agent with explicit user approvals; study its plan/act and tool-approval UX.

This is a discovery shortlist, not an endorsement or completed security review. Popularity metrics in third-party lists are mutable and may be inaccurate; verify stars, commits, releases, license, and security status directly at each canonical repository before decisions.

## 3. MCP security and integration architecture

MCP Apps documentation describes OAuth-based authorization approaches, including per-server and per-tool authorization. This supports a Kymex design that grants access at the narrowest useful scope rather than treating every tool on a server as equally trusted.

**Kymex requirements:** connector registry; OAuth discovery and token validation; per-server/per-tool scopes; least privilege; explicit consent; schema validation; sandboxing; timeout/output limits; revocation; audit events; provider health checks; and approval classes for side effects. Treat all server output as untrusted data. A catalogue count must be deduplicated and dated; do not state a 20,000+ MCP ecosystem figure without verifiable evidence.

## 4. Source list

1. OpenAI Help Center — ChatGPT release notes: https://help.openai.com/en/articles/6825453-chatgpt-release-notes
2. OpenAI Help Center — ChatGPT capabilities overview: https://help-lb.openai.com/en/articles/9260256-chatgpt-capabilities-overview
3. OpenAI Help Center — ChatGPT Work and Codex: https://help-lb.openai.com/en/articles/20001275-chatgpt-work-and-codex
4. OpenAI Help Center — Projects in ChatGPT: https://help.openai.com/en/articles/10169521-projects-in-chatgpt
5. MCP Apps — Authorization: https://apps.extensions.modelcontextprotocol.io/api/documents/authorization.html
6. Open-source agent landscape discovery index: https://github.com/upgundecha/awesome-personal-agents
7. Open-source agent landscape discovery index: https://github.com/glincker/awesome-selfhosted-ai
8. Candidate agent list: https://github.com/NousResearch/hermes-agent
9. Candidate agent list: https://github.com/HKUDS/nanobot
10. Candidate agent list: https://github.com/bytedance/deer-flow
11. Candidate browser automation: https://github.com/microsoft/playwright-mcp
12. Candidate browser automation: https://github.com/browser-use/browser-use

## 5. Verification gaps and next research

- Verify each candidate directly from its canonical repository: license, latest commit/release, supported transports, dependencies, security advisories, deployment and hosting requirements.
- Inspect official OpenAI API documentation for each modality and tool; separate API capabilities from ChatGPT-only product features.
- Determine which ChatGPT feature families Kymex can reproduce with its own backend and which require external vendors or cannot be replicated.
- Compare persistent browser approaches, user takeover, remote browser sessions, and computer-use sandboxing.
- Build a dated MCP inventory from canonical registries and repositories; deduplicate forks, archived servers, and stale entries.
- Research open-weight models and genuinely free deployment options with explicit GPU, bandwidth, storage, and inference cost assumptions.
- Record all conclusions as verified/unverified and preserve source dates.

## 6. Confidence

- **High confidence:** Public OpenAI help documentation describes the listed ChatGPT product families and Work/Codex distinction.
- **Moderate confidence:** The named agent projects are relevant discovery candidates based on public repository indexes and known project identities.
- **Not yet verified:** Current maintenance status, security posture, exact feature completeness, cost, licensing changes, and production suitability of each candidate.
- **Not established:** Any claim that there are 20,000+ currently active, safe, unique, compatible MCP servers or connectors.
