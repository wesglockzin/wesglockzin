## Hi, I'm Wes

Federal identity engineer. On-prem AI. Python.

I run identity infrastructure at federation scale — ADFS, Okta, Duo,
Entra ID — and I build the tools that keep large migrations survivable.
The ADFS-to-Okta cutover for roughly 400 applications landed in October;
now it's replacing an enterprise MFA platform mid-flight, without breaking
anyone's Monday morning.

---

### How I work

Elegance, harmony, and adherence to community standards — applied to
identity systems that have spent decades accumulating workarounds. The
goal isn't to add another clever layer. It's to find the cleaner shape
that was always there.

My daily development runs through Claude Code — hooks, persistent memory,
MCP servers, multi-model adversarial review, gated deploy pipelines — and
the patterns worth keeping get codified into methodology.

Every README here ends with a **Known limitations** section. I'd rather
tell you where my tools are weak than have you find out.

---

### The tools

**[adfs-to-okta-migration](https://github.com/wesglockzin/adfs-to-okta-migration)**
Parses ADFS Relying Party Trust exports and creates matching Okta
SAML 2.0 apps through the API — export → scan → import, with idempotent
re-runs and per-run logging. The workhorse of the migration.

**[federated-claims-analyzer](https://github.com/wesglockzin/federated-claims-analyzer)**
Interactive SSO tester. Runs a real OIDC or SAML sign-in against Okta or
ADFS and shows every claim, token, and assertion that came back — JWKS
validation, PKCE, signed SAML, the works. My ground-truth tool when a
federation flow misbehaves.

**[saml-metadata-parser](https://github.com/wesglockzin/saml-metadata-parser)**
Reads SAML metadata so I don't have to — endpoints, bindings, and every
X.509 certificate decoded with fingerprints and validity dates.

**[okta-admin](https://github.com/wesglockzin/okta-admin)**
Bulk Okta app administration across orgs — inventory, policy and routing-rule
assignment, activate/deactivate, and clearing the Everyone group with a live
view of Okta's background cleanup. It skips what Okta would reject, so a batch
never fails halfway.

**[okta-change-auditor](https://github.com/wesglockzin/okta-change-auditor)**
Who changed what, and when. A read-only view of Okta admin changes across orgs,
straight from the System Log, with routine noise filtered out. The fastest
answer to "who touched this app?"

**[okta-live-tail](https://github.com/wesglockzin/okta-live-tail)**
The Okta System Log in real time, per event, failures included — what I watch
while a sign-in is being debugged. Authenticates with OAuth client credentials
and `private_key_jwt`, so there's no shared secret to leak.

**[claude-code-session-memory](https://github.com/wesglockzin/claude-code-session-memory)**
Local RAG session memory for Claude Code — a `UserPromptSubmit` hook that
retrieves memory files by meaning, on-device, with a measured and
regression-gated eval harness. The eval story is the point: pre-committed
bars, adversarial query sets, and per-run manifests that tell a retrieval
regression from corpus drift.

**[local-rag-mcp](https://github.com/wesglockzin/local-rag-mcp)**
A read-only MCP server over the same local retrieval substrate — semantic
search served to any MCP client, symlink-hardened file access, embed-then-swap
ingest, nothing leaving the host. One substrate, two consumers.

**[identity-llm-client](https://github.com/wesglockzin/identity-llm-client)**
Small, dependency-free client for local LLM inference via Ollama.
Exists because of the next section.

---

### Why the AI here runs locally

Identity data — SAML assertions, auth logs, federation configs — can't
go to cloud AI APIs. That constraint isn't negotiable, so the interesting
engineering is making AI useful *inside* the perimeter: Ollama serving
local models, one shared client so every tool calls inference the same
way, an analysis layer in the migration tool that never sends a byte
off-host — and a retrieval pipeline with a measured eval harness, now
published as
[claude-code-session-memory](https://github.com/wesglockzin/claude-code-session-memory).

---

### About these repos

Sanitized snapshots of internal tooling, published through an automated
review-and-sanitize pipeline. Commit histories reflect publication
moments, not original development. The pipeline enforces its own gates:
every staged file must compile, every certificate must decode to a
dummy, and a deny-list of identifiers must come back empty — because a
scrub you don't verify is a leak you haven't found yet.

---

### Stack

Python · Flask · Azure Container Apps · OpenShift · Okta · ADFS · Duo ·
SAML 2.0 · OIDC · Splunk · Ollama · on-prem LLMs

---

📫 wes.glockzin@gmail.com
