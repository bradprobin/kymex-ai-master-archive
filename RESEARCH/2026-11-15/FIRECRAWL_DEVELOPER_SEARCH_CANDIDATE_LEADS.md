# Firecrawl Developer Search — Additional Candidate Leads
**Collected:** 2026-11-15  
**Scope:** Targeted developer-index searches across personal agents, app builders, MCP gateways and device/computer-use.  
**Evidence status:** Discovery leads from indexed repository/issue/docs passages. Candidates require direct repository inspection, license and release verification before adoption.

## Personal agent and assistant candidates
- OpenClaw — https://github.com/openclaw/openclaw. Indexed discovery points to persistent personal-agent behavior, messaging channels, scheduling, memory, MCP and browser automation. Search also surfaced issue #140473 describing an exec tool exposure problem in a specific backend/bridge combination. This is a security/reliability signal, not proof of a current unresolved defect; inspect issue state, affected version and fix before adoption.
- Hermes Agent — https://github.com/NousResearch/hermes-agent. Surfaced in an agent framework catalogue. Verify exact current features, license, supported channels, runtime security and release state from primary repository sources.
- nanobot — https://github.com/HKUDS/nanobot. Surfaced as a lightweight Python personal assistant with MCP and multiple messaging-channel claims. Verify current repo identity, project status, license and channel support.
- Moltis — https://github.com/moltis-org/moltis. Indexed MCP directory describes a Rust persistent personal-agent server with sandboxed execution, multi-provider models, voice, memory and messaging channels. Treat these as catalogue claims pending direct verification.
- OpenAgent — canonical repository URL not established by search result. Catalogue result described a self-hostable assistant with computer/browser use, coding, provider support, workflow builder and MCP; resolve exact project identity before adoption.

## AI application builders
- AI App Builder Open — https://github.com/totalumlabs/ai-app-builder-open. Search excerpt claims prompt-to-full-stack Next.js app generation with hosting, sandbox, database, auth and AI integration. Inspect architecture, license, deployment dependencies and whether hosting is truly included or externally billed.
- Libra AI — https://github.com/nextify-limited/libra. README-index excerpt describes a self-hostable full-stack builder and AGPL-3.0 licensing. AGPL network-service obligations may conflict with proprietary hosted Kymex deployment; obtain legal review before incorporating code.
- Vibra Code — https://github.com/sa4hnd/vibra-code. Indexed description positions it as a self-hosted mobile-app builder. Verify license, build pipeline, supported mobile frameworks, sandbox and generated app quality.

## MCP registry and gateway leads
- MCP Gateway Registry — https://github.com/agentic-community/mcp-gateway-registry. Indexed docs describe centralized discovery, gateway routing, authentication, fine-grained tool scopes and health status. Search surfaced an OAuth-support issue; verify whether resolved and whether gateway authentication is separated from downstream provider authorization.
- GitHub Agentic Workflows MCP gateway docs — https://github.com/github/gh-aw/blob/main/docs/src/content/docs/reference/mcp-gateway.md. Configuration/reference lead; verify current docs and version.

## Device and computer-use candidates
- agent-device — https://github.com/callstack/agent-device. Docs describe a CLI, MCP server and Node API for app inspection/control across iOS, Android, HarmonyOS, TV platforms, macOS, Linux and limited web targets. It collects screenshots, recordings, logs, network traces and performance evidence. Strong candidate for Kymex app QA; verify device cloud requirements and platform limits.
- Agent Sandbox (Kubernetes SIGs) — https://agent-sandbox.sigs.k8s.io/. Docs describe isolated graphical desktop/browser environments and sandbox SDKs. Evaluate for cloud computer-use isolation, but validate network isolation separately; desktop isolation alone does not guarantee safe network boundaries.
- agent-desktop — https://github.com/vercel-labs/agent-desktop. Indexed package metadata showed Apache-2.0 and desktop accessibility-tree automation. Inspect supported OS targets and sandbox provider constraints.
- Browser Use — https://github.com/browser-use/browser-use. Open-source browser agent lead. Indexed snippet mentions cloud-browser pricing; verify current rates and distinguish self-hosted automation from paid cloud browser.

## Research conclusions
1. Strong new Kymex lane: a device QA layer. agent-device may let coding agents test Kymex's actual Android/iOS/web apps and return reproducible evidence.
2. Agent Sandbox and agent-desktop may contribute isolated computer-use workers, but isolation boundaries must be independently tested, especially network egress and host access.
3. OpenClaw and lightweight assistant projects are architecture references, not automatic runtime choices. Inspect execution policies and secret handling.
4. AI app-builder projects must be screened for AGPL/copyleft obligations, hosted service dependencies and actual backend completeness.
5. MCP gateway projects need threat-model review of OAuth token propagation, user/tenant identity, tool-level scopes, SSRF and server discovery.

## Next Firecrawl scraping targets
- https://github.com/callstack/agent-device — README, docs, releases, license, platform support and MCP server implementation.
- https://github.com/agentic-community/mcp-gateway-registry — README, release notes, OAuth issue, auth middleware, registry and gateway deployment docs.
- https://github.com/totalumlabs/ai-app-builder-open — source tree, license, backend/auth/database/hosting architecture.
- https://github.com/nextify-limited/libra — deployment docs and AGPL compliance implications.
- https://github.com/openclaw/openclaw — security model, execution permissions, channels, release history and current issue status.
- https://agent-sandbox.sigs.k8s.io/docs/use-cases/computer-use/ — isolation model and deployment requirements.

No repository code was executed and no integration was installed.