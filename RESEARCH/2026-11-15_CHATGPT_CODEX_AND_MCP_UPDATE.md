# Kymex AI — ChatGPT, Codex and MCP update
**Research date:** 2026-11-15  
**Evidence window:** Public documentation available on the research date.  
**Status:** Source-grounded update; not a hands-on product test.

## 1. Codex CLI — 2026-11-13 release

The official ChatGPT & Codex changelog lists Codex CLI 0.169.0 on November 13, 2026. Notable changes include:
- Multiple side-chat tabs in the opt-in terminal workspace.
- Search older tasks by name, prompt preview, or working directory.
- Collapse completed turn details while retaining searchable tool output.
- Add/edit custom model providers from the terminal, including supported device-code onboarding for gateways.
- Save a diagnostic ZIP locally from the terminal report editor.
- Opt-in Cloud connection improvements for macOS/Linux, including image input, model/reasoning selection, and archive/restore of Cloud conversations.

The same release notes mention safety fixes that keep project configuration and MCP servers disabled in untrusted directories unless the user explicitly trusts the project, and fixes to MCP server wait behavior and interrupted turns.

**Kymex implications**
1. Add task-history search across agent runs, indexed by task name, prompt, project, working directory, provider, and date.
2. Support multiple concurrent task conversations in a project workspace without mixing context.
3. Add collapsible execution details with searchable tool logs and preserved final summaries.
4. Support custom model gateways only through explicit configuration and credential-safe device authorization where supported.
5. Generate diagnostic bundles that exclude secrets and private user content by default.
6. Treat project trust as a first-class security boundary: do not load project MCP configuration, scripts, or tool definitions from an untrusted repository without explicit approval.
7. Ensure interrupted/cancelled jobs release locks and do not corrupt later tasks.

## 2. ChatGPT Dots — ongoing agent pattern

The current official What's New digest reports custom instructions for a dot (November 9–13). Earlier entries describe notification replies, mobile messaging, shortcuts, and ongoing agents with connected apps and cloud-computer execution. These are ChatGPT product rollouts and availability is plan/region dependent.

**Kymex implications**
- Provide a persistent agent identity with editable behavior instructions.
- Let a user delegate an ongoing goal with explicit scope, connected tools, autonomy level, and review requirements.
- Support asynchronous status updates and resumable work.
- Offer a notification/command channel that routes to the durable backend, not a separate execution engine.
- Keep autonomy policy visible and revocable; a persistent agent must not silently expand its permissions.

Do not claim Kymex has a ChatGPT-style cloud computer until it is implemented, isolated, monitored, and verified.

## 3. MCP specification and authorization security

The MCP 2026-07-28 specification announcement describes a stateless protocol core, multi-round-trip requests, header-based routing, cacheable list results, authorization hardening, and a formal extensions framework.

The official authorization security guidance requires OAuth 2.1 security practices and emphasizes token audience binding/validation, secure token storage, short-lived tokens where appropriate, refresh-token rotation for public clients, HTTPS, PKCE protections, exact redirect URI validation, state validation, and rejection of tokens not intended for the receiving MCP server. It explicitly prohibits passing a token received from the MCP client through to an upstream API as if it were an upstream token.

**Kymex implementation requirements**
1. Bind access tokens to the intended MCP resource/audience and validate audience server-side.
2. Never forward a client's MCP access token to a different upstream service; obtain a separate upstream credential through the correct authorization flow.
3. Use PKCE and verify supported challenge methods; fail closed if required metadata is missing.
4. Register and exactly validate redirect URIs; validate OAuth state and authorization responses.
5. Protect tokens at rest, redact them from logs, and provide revocation and rotation.
6. Keep each connector's scopes and grants isolated; do not reuse a broad credential across unrelated servers.
7. Treat connector outputs and tool descriptions as untrusted inputs, with prompt-injection defenses and explicit side-effect policy.

## 4. Sources

1. ChatGPT & Codex changelog (November 13, 2026): https://learn.chatgpt.com/docs/changelog
2. ChatGPT What's New (November 9–13, 2026): https://learn.chatgpt.com/docs/whats-new
3. OpenAI ChatGPT release notes: https://help.openai.com/en/articles/6825453-chatgpt-release-notes
4. MCP 2026-07-28 specification announcement: https://blog.modelcontextprotocol.io/posts/2026-07-28/
5. MCP authorization security considerations: https://github.com/modelcontextprotocol/modelcontextprotocol/blob/main/docs/specification/2026-07-28/basic/authorization/security-considerations.mdx

## 5. Verification notes

- These findings are based on public documentation, not a live Kymex integration test.
- Product availability varies by plan, workspace, rollout, and region.
- Codex CLI release notes do not prove that every feature is exposed through a public API.
- MCP protocol conformance does not certify a third-party server as safe.
