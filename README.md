## Hi, I'm Wes

Federal identity engineer. On-prem AI. Python.

I run identity infrastructure at federation scale — ADFS, Okta, Duo,
Entra ID — and I build the tools that keep large migrations survivable.
Right now that means moving roughly 400 applications from ADFS to Okta
and replacing an enterprise MFA platform mid-flight, without breaking
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

**[identity-llm-client](https://github.com/wesglockzin/identity-llm-client)**
Small, dependency-free client for local LLM inference via Ollama.
Exists because of the next section.

---

### Why the AI here runs locally

Identity data — SAML assertions, auth logs, federation configs — can't
go to cloud AI APIs. That constraint isn't negotiable, so the interesting
engineering is making AI useful *inside* the perimeter: Ollama serving
local models, one shared client so every tool calls inference the same
way, and an analysis layer in the migration tool that never sends a byte
off-host. Next up for publication: a local retrieval pipeline with a
measured eval harness.

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
