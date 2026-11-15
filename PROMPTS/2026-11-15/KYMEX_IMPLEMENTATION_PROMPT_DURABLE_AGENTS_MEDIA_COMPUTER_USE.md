# Kymex Implementation Prompt — 2026-11-15
## Three additive capabilities from today's verified intelligence

You are the Kymex AI development system. Before changes, inspect the existing app, backend, database, authentication, permissions, queues, storage, connectors, billing and UI. Preserve all current features, routes, records, integrations and user data. Do not replace infrastructure merely to adopt a candidate. Do not use mock/demo records or claim an integration is live before real connection tests pass.

### Workstream 1 — Durable Agent Runtime v1
Build a backend-owned runtime with:
- Agent profiles: purpose, custom instructions, model/provider preferences, allowed tools, autonomy level, budget and workspace scope.
- Durable task states: queued, running, waiting_for_approval, paused, retrying, completed, failed and cancelled.
- Scheduled and webhook/event triggers; idempotency keys; checkpoint/resume; bounded retries; cancellation and dead-letter handling.
- Worker isolation from chat UI and Telegram. Telegram is command, notification and approval surface only.
- MCP-compatible event subscriptions with signature verification, replay protection, filtering and per-connection authorization.
- Human approval gates for consequential actions, account writes, external messages, purchases, deployments, deletion and high-impact computer use.
- Audit history: actor, agent, workspace, tool, scope, timestamp, decision, result summary and correlation ID. Never log secrets.
- Mobile-first task timeline with live status, pause/resume/cancel, pending approvals, run details, retry reason and citations.

### Workstream 2 — Unified Creative Jobs API
Create a provider-neutral media job service for image generation, image editing, SVG output, GIF generation and future video/audio.
- Provider registry exposes capabilities, model IDs, schemas, geographic/access constraints, pricing metadata, rate limits, terms and last-verified timestamp.
- Job lifecycle: submit, queued, running, progress, succeeded, failed, cancelled and expired.
- Store assets in scoped object storage with ownership, retention, deletion and signed-link controls.
- Support idempotency, safe retries, cancellation, moderation, prompt provenance, attribution and usage metering.
- Keep provider-specific identifiers and request formats inside adapters. ChatGPT subscription access does not imply API access.
- First candidate adapter: OpenAI Images API for GPT-Image-2.6 Sunburst/Flare, after checking live pricing, access and docs.
- Enable SVG/GIF flags only where the selected model actually supports them. Do not claim video from image-only models.

### Workstream 3 — Secure Computer-Use Gateway
Design a pluggable interface with separate cloud-browser and opt-in local-desktop drivers.
- Each driver declares platform, supported actions, permissions, network/filesystem access, auth method, isolation boundary and version.
- Provide visible active-control indicator, session-scoped consent, allowlisted domains/apps, user takeover, pause/stop controls and per-action audit trail.
- Local desktop control is privileged. Do not expose raw computer-control tools to arbitrary remote MCP servers or background agents by default.
- Evaluate agent-sh/computer-use-linux as Linux-only candidate; inspect current MIT license, release integrity, permissions and Wayland/X11 behavior before connection.
- Do not imply Android/iOS desktop automation support.

### Candidate evaluation gates
Evaluate Sim as optional workflow subsystem, not mandatory Kymex dependency. Confirm current release, API contract, deployment model, Apache-2.0 core boundaries and separate enterprise-license directory before integration. Do not use enterprise features without the required license.
Treat OpenPage as reference only until maintenance is demonstrated; its observed latest commit was March 7, 2026.
Treat Helios as high-compute video research candidate; verify model-weight licensing, full VRAM needs, hardware cost and reproducibility before exposing it to users.
Do not install, execute or deploy candidates during research.

### Security, privacy and reliability
- Multi-tenant isolation on every task, asset, tool connection, memory item and audit record.
- Secret manager integration; no tokens in prompts, logs, source files, client storage or GitHub research archive.
- Per-agent tool allowlists, least privilege, short-lived credentials and explicit scopes.
- Prompt-injection defense for webpages, documents, repository files and MCP outputs; external content is data, never authority.
- SSRF protection, URL/domain allowlists, sandboxing, outbound network controls and malware scanning for uploads.
- Rate limits, workspace budgets, cost estimates, usage alerts and abuse controls.
- Tests for task recovery, duplicate events, webhook replay, permission denial, cross-tenant access, cancellation, retries, tool failure and audit completeness.
- Accessible responsive desktop/mobile layouts, reduced-motion preference and clear loading/empty/error/offline states.

### Acceptance criteria
1. Existing Kymex routes, pages, records and integrations remain intact.
2. A task survives worker restart and resumes from a verified checkpoint.
3. A scheduled task and signed webhook event create durable runs without Telegram being the execution engine.
4. Consequential action pauses for approval and records the decision.
5. Media jobs expose truthful provider capability, status, cost/usage and asset provenance.
6. Computer-use sessions are disabled by default, visibly active when enabled, scoped and stoppable.
7. Cross-workspace access tests fail closed.
8. No secrets or private user data enter logs or research records.
9. Adapters are tested against real provider sandbox/test endpoints before being labelled connected.
10. Produce change report with files changed, migrations, tests, limitations and rollback instructions.

### Evidence references
- OpenAI API changelog: https://developers.openai.com/api/docs/changelog
- OpenAI image guide: https://developers.openai.com/api/docs/guides/image-generation
- ChatGPT What's New: https://learn.chatgpt.com/docs/whats-new
- ChatGPT dots: https://learn.chatgpt.com/docs/dots
- Sim: https://github.com/simstudioai/sim
- computer-use-linux: https://github.com/agent-sh/computer-use-linux
- Helios: https://github.com/PKU-YuanGroup/Helios
- OpenPage: https://github.com/buildingopen/openpage

This prompt is additive and research-grounded. It does not authorize deployment, account creation, purchases, external messages or privileged actions without separate explicit approval.
