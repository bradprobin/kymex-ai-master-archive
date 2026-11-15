# KYMEX AI — Current Implementation Addendum
**Release:** 2026-11-15  
**Status:** Additive requirements; preserve all historical Kymex source prompts.  
**Purpose:** Current working implementation direction, not a replacement for the historical master.

## 0. Non-destructive migration directive

This addendum extends the existing Kymex specification. Preserve every prior requirement, page, workflow, provider adapter, security control, and implementation decision unless the user explicitly approves a change. Resolve conflicts by documenting them in a dated decision record; do not silently discard older material. Keep source text, verified research, and new recommendations clearly distinguished.

## 1. Product definition

Build Kymex AI as a persistent personal AI operating workspace—not merely a chatbot and not a thin wrapper around one model. It should coordinate conversational assistance, long-running delegated work, research, coding, app/site creation, browser and computer use, files, data analysis, documents, image/video/audio generation, voice, workflows, messaging, integrations, MCP tools, and administration.

The user-facing experience should combine:
- A fast conversational interface for everyday requests.
- A task/work mode for multi-step work with visible plans, progress, artifacts, approvals, and resumability.
- A coding/developer workspace connected to repositories, branches, diffs, tests, and deployments.
- A persistent browser workspace with live page view, agent activity, and explicit user takeover when supported.
- A unified project/workspace system for chats, files, code, websites, media, agents, and tasks.
- A mobile-first experience with a coherent desktop layout and accessible interaction patterns.

## 2. ChatGPT capability-parity research and implementation

Maintain a capability matrix against the current ChatGPT product. Research and implement equivalent Kymex workflows where technically and legally feasible, without claiming access to OpenAI internal systems or private product infrastructure.

Evaluate these capability families independently:
1. Conversation, model selection, reasoning modes, context handling, and structured outputs.
2. Web search, source-grounded research, multi-step deep research, citations, and report generation.
3. File uploads, extraction, search, long-document analysis, and persistent project knowledge.
4. Data analysis, code execution, tables, charts, spreadsheets, and generated downloadable artifacts.
5. Image understanding, image generation, image editing, and visual references.
6. Voice input/output, speech transcription, interruption, and voice-driven task execution.
7. Projects, project-specific instructions, persistent context, and controlled memory.
8. Scheduled and conditional tasks, recurring research, monitoring, and notifications.
9. Connected apps/plugins, scoped permissions, OAuth, and multi-step actions.
10. Browser automation, computer use, user takeover, screenshots, and page-state observation.
11. Coding agents, repository operations, tests, code review, and deployment workflows.
12. Custom agents, reusable skills, tool discovery, and specialist-agent orchestration.

For each item record: product capability; public API availability; third-party implementation path; required credentials; region/plan constraints; data handling; cost; reliability; user approval class; and whether the Kymex implementation is complete, partial, experimental, or unavailable. Distinguish ChatGPT product functionality from features exposed by OpenAI APIs. Do not assume product features are directly callable through an API.

## 3. Model and provider orchestration

Implement a provider-neutral model registry and adapter layer. Support multiple model families and routing policies where integrations are actually configured. Model routing must consider task type, quality, latency, context window, modality, availability, cost limits, data sensitivity, and user preference.

Requirements:
- User-selectable model/provider where available.
- Automatic routing with a visible explanation and override.
- Fallbacks only to configured, permitted providers.
- Normalize tool calls, streaming, usage, errors, and artifact outputs.
- Record model/provider provenance for generated artifacts.
- Never imply that a provider is connected merely because it appears in a catalogue.
- Provide per-workspace provider allowlists and budget controls.

## 4. Agent runtime and long-running work

Use a durable orchestration layer with task IDs, state transitions, checkpoints, resumability, cancellation, retries, idempotency, deadlines, and observable progress. Separate planning from execution. Support specialist subagents for research, coding, browser work, data analysis, media, documents, and operations, with explicit delegation boundaries and shared task context.

Each task must expose:
- User goal and interpreted constraints.
- Proposed plan and current step.
- Tools/providers selected and why.
- Approval requirements and pending actions.
- Progress, outputs, errors, retries, and timestamps.
- Final verification evidence and a truthful completion summary.

Do not mark a task complete because a model generated a plausible response. Verify external state where the operation changes an external system.

## 5. Browser and computer-use workspace

Provide an authorized browser/computer-use capability that can navigate supported websites, inspect page state, click, type, upload/download, and complete multi-step workflows. Where supported, show the live browser view and allow the user to take over and return control.

Security requirements:
- Isolate browser sessions by user and workspace.
- Store credentials in a managed secret vault; never in prompts, logs, or repository files.
- Use scoped sessions and least-privilege permissions.
- Detect login, MFA, CAPTCHA, payment, legal consent, and other sensitive checkpoints; pause for the user when required.
- Treat page content and downloaded files as untrusted instructions.
- Require explicit confirmation for consequential actions such as sending, publishing, purchasing, booking, deleting, transferring money, or changing account security.
- Record action provenance and verify resulting state.

## 6. MCP and integration ecosystem

Build an MCP client/registry that can discover and connect user-authorized MCP servers and conventional app integrations. Do not hardcode a claimed ecosystem size (including claims such as 20,000+ servers/connectors) without a dated, deduplicated, independently verifiable catalogue.

Each connector record must include:
- Canonical name, owner, source URL, version, license, and maintenance signals.
- Transport and protocol compatibility.
- Authentication/OAuth requirements and scopes.
- Declared tools/resources/prompts and input/output schemas.
- Data access and side-effect classification.
- Trust/risk score, sandboxing requirements, and provenance.
- Health, latency, rate limits, cost, and last verification date.

Apply schema validation, allowlists, user consent, least privilege, server-side authorization, per-tool approval, timeouts, output limits, audit logs, and revocation. Tool output is untrusted data and must never override system or user instructions. Provide connector health checks and a clear disconnect/revoke flow.

## 7. Research, web intelligence, and knowledge

Support both quick search and multi-step research. Search official documentation and canonical repositories first; use community sources as supplementary evidence. Record exact URLs, retrieval date, publication/update date where known, version/commit, license, and confidence. Separate facts, claims, assumptions, and recommendations.

Research tracks:
- Personal AI agents and agent runtimes.
- AI website/app builders and code-generation systems.
- Coding agents and IDE integrations.
- Browser automation and computer-use frameworks.
- MCP clients, servers, directories, and security practices.
- Image, video, voice, avatar, and audio generation.
- Workflow engines, queues, schedulers, and durable execution.
- Storage, databases, authentication, hosting, observability, and deployment.
- Open-weight/local models and low-cost infrastructure.
- ChatGPT product capabilities versus public OpenAI API capabilities.

Never equate GitHub stars with quality, maintenance, security, or production readiness. Check recent commits, releases, issues, license, dependencies, security advisories, and actual installation requirements.

## 8. Telegram command center

Telegram may serve as a command and notification interface, but it must not be the execution engine. Commands should authenticate to the persistent Kymex backend, create durable tasks, and return status/artifact links. The backend owns task state, policy enforcement, memory, tool routing, and audit records. Support secure account linking, revocation, per-chat authorization, rate limits, and protection against spoofed updates.

## 9. Persistent memory and workspaces

Provide user-controlled memory with source attribution, timestamps, confidence, edit/export/delete controls, retention settings, and workspace boundaries. Distinguish durable user-approved preferences from temporary task context. Never store secrets as memory. Provide project/workspace-specific instructions and knowledge retrieval with permission filtering.

## 10. App Control Center

Preserve and extend the existing Control Center with the functional categories:
- Look and Feel
- Data and Files
- Power
- Run It
- Advanced

Include project/app overview, database, files, storage, agents/bots, workflows, integrations, GitHub sync, billing, analytics, domains, security, deployments, logs, and environment configuration as applicable. Every page needs a real backend contract, authorization, loading/empty/error states, mobile layout, audit events, and tests. Navigation visibility is not authorization.

## 11. Design and interaction quality

Use a polished, coherent, responsive interface with restrained visual effects, clear typography, consistent outline iconography, accessible contrast, keyboard support, and touch targets. Provide light/dark themes and persistent navigation context. Motion must communicate state or hierarchy rather than slow down work. Optimize perceived and actual performance with route-level loading, pagination, caching, and background jobs.

## 12. Security, privacy, and governance

Enforce tenant isolation, role-based access, least privilege, secret management, encryption in transit/at rest, audit trails, retention controls, secure file handling, prompt-injection defenses, output validation, rate limits, abuse prevention, and incident response. Apply human approval to high-impact actions. Never expose another user's files, chats, credentials, or task state. Do not store personal secrets or raw credentials in GitHub.

## 13. Quality gates and acceptance

For every capability, provide:
- Backend contract and data model.
- UI states and accessibility behavior.
- Authorization and consent model.
- Provider adapter and failure handling.
- Observability and audit events.
- Unit, integration, end-to-end, security, and regression tests.
- Cost/usage accounting and limits.
- Documentation and operational runbook.

A feature is not complete until its happy path, empty state, denial path, provider outage, timeout, retry, cancellation, and recovery paths are tested. Use real integrations in staging where possible; clearly label mocks and never seed fake production data.

## 14. Current daily workstreams

Maintain two independent daily deliverables:
1. **Daily Kymex Implementation Prompts** — actionable, additive implementation prompts based on verified new research and the existing Kymex backlog. Each entry includes date, objective, scope, prerequisites, implementation steps, files/modules affected, security implications, acceptance criteria, and rollback notes.
2. **Daily AI Intelligence Report** — concise dated intelligence on significant model, agent, builder, MCP, browser, coding, media, infrastructure, and automation developments, with source links, verification status, and concrete Kymex implications.

Avoid duplicate findings. Track already-covered items and explicitly flag uncertain or unverified claims. A scheduled task's successful run is not proof that GitHub archival succeeded; verify each commit and report failures.

## 15. Immediate implementation priorities

1. Preserve and transfer the full historical prompt byte-for-byte; verify SHA-256 and byte size.
2. Reconcile the recovered historical prompt with the latest user decisions from November 13–15, 2026; append changes without rewriting history.
3. Build a current ChatGPT capability matrix separating product features from public APIs.
4. Establish a verified MCP/connector catalogue with security and maintenance metadata; do not assume a 20,000+ count.
5. Validate the agent runtime, persistent browser/user takeover, Telegram command center, and durable task architecture.
6. Convert verified research into small, testable, additive implementation prompts.
7. Maintain dated research and prompt indexes with commit-level provenance.

**Completion honesty:** This document is an additive working prompt. It does not assert that any listed capability has already been implemented, connected, tested, or deployed.
