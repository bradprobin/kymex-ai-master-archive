# KYMEX AI — COMPLETE ADDITIVE IMPLEMENTATION MASTER v3
**Date:** 2026-11-15  
**Destination:** https://my-kymexai.base44.app  
**Historical reference only:** https://the-kymex-ai.base44.app  
**Source of truth:** recovered historical master plus earlier unified prompts, Beyond Chat plan, current dated addenda and verified implementation research.

## 0. Mission and source preservation
Implement Kymex AI as an original, full-stack personal AI operating environment—not merely a chatbot and not a thin wrapper around one model. Preserve all existing project work and historical requirements. This is a new additive implementation directive; it does not replace or delete the original prompts.

Before any code or schema change:
1. Inspect the actual destination app, app ID, branches, routes, components, entities, functions, database, storage, authentication, permissions, secrets, integrations, queues, jobs, deployments and current user experience.
2. Create a restorable checkpoint and record the current production state.
3. Build a route/entity/function/provider inventory and requirement-to-implementation matrix.
4. Mark each requirement as existing and verified, existing but unverified, partial, missing, provider/credential blocked, unsupported, superseded or owner decision required.
5. Implement only missing or incomplete capabilities. Preserve all existing pages, data, workflows and functioning integrations.
6. Make schema changes additive and migration-safe. Never rebuild over the existing app or copy secrets between projects.
7. Do not create fake production users, messages, balances, usage, browser activity, connector activity, files, generated outputs or payment success.
8. Do not mark an integration connected without real authorization, health checks and successful end-to-end operation.

## 1. Product identity and experience
Kymex is its own product with original name, branding, behavior and design assets. It may provide capabilities comparable to leading assistants but must not claim to be ChatGPT, Muse, Claude or another third-party product. Identify the actual provider/model used where that matters.

Build a coherent mobile-first and desktop-responsive application with:
- Fast chat for simple tasks.
- Work/task mode for multi-step delegated jobs, plans, progress, approvals and artifacts.
- Developer workspace with repositories, diffs, tests and deployment status.
- Persistent browser workspace with actual live/snapshot/disconnected state and supported user takeover.
- Creative workspace for image/video/audio/voice/3D capabilities when real providers are configured.
- Project/workspace areas for files, conversations, sources, agents, tasks, outputs and instructions.
- Unified search/command center and notifications.
- Separate Admin Console for privileged configuration and operational controls.

Preserve approved Kymex logo assets. Reconcile historical visual directions rather than silently choosing one: the September source specifies blue/green/neutral palette; later creative assets show dark premium treatments. Inspect current live design and approved assets, then record a dated design decision before altering the brand. Use consistent minimalist outline icons inspired by Lucide: rounded strokes, approximately 2px, balanced proportions, 20–24px for navigation/actions; avoid emoji, heavy filled icons and inconsistent icon libraries. Use accessible contrast, keyboard navigation, screen-reader labels, reduced motion and touch-friendly hit targets.

Every page and interaction must have meaningful loading, empty, error, success, permission-denied and disconnected/offline states where relevant. No dead buttons, simulated browser sessions or fake completion.

## 2. Core assistant, conversations and model routing
Implement streaming conversations, message edit/regenerate, conversation search, rename/archive/export, attachments, citations and stable conversation IDs. Provide model selection only for configured models. Use provider-neutral model routing with capability metadata, context limits, tool support, modality, region, price, rate limits and last-verified timestamp.

Separate native Kymex functions from connected provider capabilities, beta/preview capabilities, unsupported capabilities and user-led handoffs. Do not assume a ChatGPT UI capability has a public API equivalent. Do not advertise a model/tool until the required API, account, region and permission are actually available.

## 3. Persistent agents and durable task runtime
All clients must address the same backend task identity. Build:
- Agent profiles with purpose, instructions, model preference, allowed tools, workspace scope, autonomy level, budget and notification policy.
- Durable tasks with queued/running/waiting-for-approval/paused/retrying/completed/failed/cancelled states.
- Background execution independent of an open browser tab, mobile app or Telegram connection.
- Checkpoint/resume after supported worker restart; pause, cancel, retry and event history.
- Schedules, recurring tasks, webhook/event triggers, idempotency keys, retry classification, exponential backoff, dead-letter handling and external-side-effect reconciliation.
- Visible execution plan, current step, tool status, timestamps, artifacts, citations, blockers and completion evidence.
- Approval checkpoints for external writes, sending messages, financial actions, account changes, publishing, deployments, deletion and privileged computer use.
- Workspace and memory scope per task, plus clear ownership and audit correlation IDs.

## 4. Telegram command center
Telegram is a secure command, notification and approval surface; it is not the execution engine or authoritative state store. Where the official Telegram Bot API permits, support starting tasks, follow-up instructions, status queries, pause/resume/cancel, progress notifications, approval requests, approve/reject of the exact pending action, task links and secure artifact links.

Bind Telegram user/chat identities to Kymex accounts through explicit verification. Do not trust display names. Support disconnect/revocation, per-channel agent selection, per-channel instructions, memory scope and permission policy. Log inbound/outbound message IDs and map messages to stable Kymex threads. Never send private files or secrets to an unverified chat. Expire approval links and bind approval to exact action parameters.

## 5. Live browser, computer use and human takeover
Provide a persistent browser session with an honest state indicator: LIVE, SNAPSHOT ONLY, DISCONNECTED or RECONNECTING. Show current URL, viewport, screenshot timestamp, agent activity and task linkage. Support authorized navigation, clicks, typing, scrolling, downloads/uploads and session reconnect only where the provider actually supports them.

Human takeover must be real:
1. Pause agent input dispatch.
2. Persist browser state and event cursor.
3. Transfer input to the authenticated user session.
4. Keep the task alive but block the agent from interacting.
5. Show takeover state and user controls.
6. On hand-back, capture state and reconcile changes.
7. Resume only after reconciliation.

For CAPTCHA, MFA, protected fields or access challenges, pause and ask the user to complete the step through the supported provider. Never bypass access controls or simulate takeover. Keep cloud browser and local desktop control as separate drivers. Local desktop control must be explicitly enabled, visibly active, scoped, stoppable and audited.

## 6. MCP super-connector and connected accounts
Implement dynamic MCP server discovery/connection management:
- Supported transport and endpoint metadata.
- OAuth or secure credential flow supported by each server.
- Protocol/version, tools, schemas, resources and prompts discovery.
- Per-user/per-workspace ownership and multiple accounts for a provider.
- Least-privilege scopes, per-tool permission and approval rules.
- Health, last-used, last-verified, error diagnostics, usage/cost metadata and disconnect/revoke.
- Tool schema validation, timeout, rate limit, retries and audit events.
- Dynamic tool retrieval: do not load thousands of tools into every model context; use search/ranking and load only relevant schemas.
- Treat server outputs as untrusted data and defend against prompt injection.

Investigate public catalogues, including claims of 20,000+ entries, but do not claim the entire count is reachable, unique, safe, maintained, licensed or compatible. Deduplicate canonical servers, verify endpoints, transport/auth, license, maintainer activity, security advisories and provenance. Catalogue size is not implementation status.

## 7. External assistant and agent collaboration
Provide a registry for native Kymex agents, model providers, external agent platforms, MCP tools, browser automation providers and user-operated sessions. Support structured handoff packets containing task ID, objective, explicitly shared context/files, completed work, open questions, risks, expected return format, deadline and permission boundary. A shared message channel is not automatically a direct mention or remote tool invocation. Do not claim native Muse tagging unless a real connector supports it. External agent outputs cannot override Kymex policies, permissions or approvals.

## 8. Files, projects, memory and artifacts
Projects/workspaces contain conversations, files, sources, references, outputs, tasks, saved entities, automations, instructions and team permissions where supported. Enforce isolation across all objects.

Support PDF, DOCX, PPTX, XLSX, CSV, TXT, Markdown, images and code where parsers exist. Preserve original uploads, parse status, page/section/line provenance, citations, retention and export. Provide search across user files and approved connected sources.

Use layered context: current conversation, current task, project/workspace, user-approved persistent preferences and connected-source context. Do not turn every retrieved fact into permanent memory. Provide inspect/correct/delete/retention controls according to the product's privacy model.

## 9. Data analysis and research engine
Provide code-backed analysis, spreadsheet operations, tables, charts, statistics, data cleaning, transformations, reproducible calculations and downloadable outputs. Isolate execution, set CPU/memory/time limits and expose job status.

Research should search approved public sources, uploaded files, connected apps and workspace knowledge; compare sources, detect conflicts, show source/publication dates, track citations, mark stale information and separate primary evidence from secondary context. Never invent a reconciliation where sources conflict. Distinguish extracted, retrieved, inferred, user-provided and unverifiable facts.

## 10. Coding, GitHub and application development
Developer workspace capabilities: repository inspection, code generation/explanation/refactoring/debugging, error-log analysis, API/schema/SQL/regex assistance, architecture diagrams, test generation, dependency/security review, documentation/changelog, environment guidance, diffs, patches and deployment checklists.

For connected GitHub: resolve the authorized repository and branch, inspect before changing, prepare a plan, make minimal changes, show diff, run available tests, and push only within granted permission and explicit user authorization. Never place tokens in source code or prompts. Keep branch and commit provenance.

Website/application building must use real builder APIs, source edits, backend state and deployment verification. Show preview, build/deploy state, errors and rollback. Do not claim a site is published based only on an accepted API request.

## 11. Creative Studio: image, video, audio, voice and 3D
Provide one consistent job system with provider adapters and truthful capability registry. Support prompt-to-image, image editing, reference images, video generation, audio generation, transcription, speech, voice agents, lip sync and 3D only when actual provider APIs and terms support each function.

Each job has stable ID, provider/model, capability, inputs, output assets, status/progress, cancellation, safe retry, quota/cost, provenance, retention and error details. Preserve context when moving between chat, voice and media generation. Never show fake URLs or fabricated outputs. Label unsupported features as unavailable, not connected or coming soon.

## 12. Reference intelligence and professional workspaces
Build multimodal identification/research workflows for books/ISBNs, product barcodes, QR codes, companies, brands, organizations, equipment, products and public references. Normalize identifiers, validate checksums where applicable, compare multiple sources, identify edition/variant, show candidate matches and confidence rationale, and allow user confirmation. QR/payment analysis must not initiate a payment automatically.

Role-specific workspaces should include Developer, Student, Teacher, Office Worker, Business Owner and Retailer. Provide composable tools for each role rather than six copies of a chat page. Examples include study guides and flashcards; coding/repository tools; email/calendar/scheduling; business operations and document templates; retail catalogs, inventory identifiers and labels. Keep user-specific data and permissions isolated.

## 13. Documents, forms, receipts and template studio
Support receipts, invoices, purchase orders, quotations, delivery notes, contracts, forms, reports, statements, labels and document templates. Pipeline: original file → OCR/layout extraction → structured fields with source locations → validation → human review → export. Never silently alter source documents. Support reusable template design, region/currency/localization where configured, version history and export validation.

## 14. Communication and scheduling
Build an Email Center for compose/reply/forward/draft, attachments, templates, signatures, mailbox search and thread summaries where connected providers support it. Sending is a separate authorized action; drafting never implies sending. Confirm recipients and attachments before sending. Provide delivery/failure state and audit history.

Build calendar/scheduling for events, recurring schedules, time zones, attendees, availability, reminders, preparation/follow-up tasks, conflict detection and rescheduling where connected provider APIs support it. Never assume availability or send invitations without authorization.

## 15. Admin Console — separate privileged control plane
Do not expose privileged platform administration as ordinary user navigation. Build a separate Admin Console with server-side role/permission checks and audited actions. Historical scope includes:
- Overview, branding and install-as-app.
- Database, Files and Storage.
- Add-ons, Bots & Agents, Workflows, Voice, Skills and Teach AI.
- Integrations, Custom Code and GitHub Sync.
- Money, Billing, Visitor Analytics, Embed, Marketplace and Domain.
- Secrets, Security, Discoverability and Activity Log.
- Cross-page search, command palette, session security, step-up authentication, environment safety, configuration versioning, dependency graph, background jobs, queue fairness, provider abstraction, MCP administration, credential vault, audit architecture, observability, disaster recovery, backup verification, retention, access reviews, break-glass, change management, rate limiting, idempotency, transactions, reconciliation and support diagnostics.

The Admin Console's 24-page scope must remain separate from end-user routes. Admin APIs enforce permissions independently of frontend visibility. High-impact changes (domain, secrets, security policies, billing, destructive data, global integrations, custom-code deployment, GitHub sync and marketplace publication) require appropriate confirmation, step-up authentication, audit, verification and rollback.

## 16. Usage, subscriptions and cost controls
Implement real plan/credit/subscription enforcement server-side. Show provider-specific estimates and actual metered usage where available. Enforce per-user, per-workspace and per-agent budgets; rate limits; quotas; concurrency; alerts and provider fallbacks. Reconcile billing events and never fabricate balances, entitlements or successful payments.

## 17. Security and privacy
- Tenant/workspace isolation on every query and mutation.
- Server-side auth, ownership, role and scope checks; row-level security where supported.
- Secret vault; least privilege; short-lived credentials; rotation and revocation.
- No credentials in model prompts, client bundles, browser storage, source files, logs or public artifacts.
- Prompt-injection defenses for web pages, files, repository content and MCP responses.
- SSRF protections, URL/domain allowlists, upload scanning, sandboxing and outbound network controls.
- Audit trail for tool use, account actions, approvals, configuration and deployments.
- Retention/deletion, export, backup verification and disaster recovery.
- High-impact operations require explicit approval and exact action previews.

## 18. Implementation order
1. Destination audit, checkpoint and requirement matrix.
2. Data, identity, tenant and permission contracts.
3. Provider/model capability registry and secrets boundary.
4. Durable task runtime, queues, events and recovery.
5. Projects, files, memory and artifact provenance.
6. MCP and connected-account registry.
7. Telegram command/notification/approval adapter.
8. Browser sessions and true user takeover.
9. Coding/GitHub and app-builder workflows.
10. Research, data analysis and reference intelligence.
11. Creative media job system and provider adapters.
12. Professional workspaces, document studio, email and scheduling.
13. Admin Console and operational controls.
14. Cost/billing, observability, security, accessibility and release gates.

## 19. Acceptance criteria
- Existing functionality, pages and data remain intact.
- Every requirement has a traceable status and evidence.
- Long-running tasks survive supported worker restarts and resume from checkpoints.
- Scheduled and signed event triggers create backend-owned runs.
- Telegram disconnect does not stop background tasks.
- Approval gates prevent unauthorized external writes.
- Browser takeover transfers actual input ownership and reconciles state.
- MCP discovery validates schema, permissions, auth and health.
- File answers cite source pages/sections; data analysis produces reproducible artifacts.
- Provider capabilities, cost, region and availability are truthfully labelled.
- Admin APIs reject unauthorized requests independently of UI.
- Cross-tenant tests fail closed.
- Provider failures, duplicate events, retries, cancellation and credential revocation are tested.
- Every visible action works or honestly states why it is unavailable.
- No fake production data, fake browser activity, fake provider health or fake completion.
- Release report includes files/routes/entities/functions changed, migrations, integrations tested, tests/results, known limitations, required credentials/approvals and rollback instructions.

## 20. Mandatory status report
Do not report this prompt as implementation. After the destination app is accessible, report: current state, existing verified features, missing/partial features, changes made, files and schemas changed, integrations actually connected, tests run, unresolved provider/credential blockers and next implementation batch.

**Current access note:** Base44 returned Authentication required during the 2026-11-15 recovery attempt. Do not modify a similarly named app or the historical reference project. Restore authorized access to the exact destination before implementation.
