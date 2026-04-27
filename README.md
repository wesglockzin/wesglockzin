## Hi, I'm Wes

Federal identity engineer. On-prem AI. Python.

I build tools that automate ugly identity and security problems —
SSO migrations at federation scale, SAML/OIDC debugging, security
monitoring, and local LLM tooling for environments where cloud AI
isn't an option.

---

### How I work

Elegance, harmony, and adherence to community standards and best practices— applied to identity systems that
have spent decades accumulating workarounds. The goal isn't to add
another clever layer. It's to find the cleaner shape that was always
there.

---

### Flagship projects

**[adfs-to-okta-migration](https://github.com/wesglockzin/adfs-to-okta-migration)**
Migrate ADFS Relying Party Trusts to Okta SAML 2.0 apps via API. Dry-run
support, conflict detection, idempotent re-runs, FIPS-compliant token
handling, multi-ACS endpoint support. Reduces manual ADFS-to-Okta
migration from hours-per-app to a repeatable workflow with audit logs.

**[federated-claims-analyzer](https://github.com/wesglockzin/federated-claims-analyzer)**
Full-stack OIDC and SAML 2.0 identity testing platform. JWT decoding,
JWKS validation, SAML assertion parsing, PKCE flows, multi-provider
support (Okta, ADFS, Azure AD), Azure Container Apps deployment.
The tool I reach for when an SSO flow is misbehaving and I need ground
truth.

**[splunk](https://github.com/wesglockzin/splunk)**
Splunk dashboard library for identity platform security monitoring.
Production dashboards covering ADFS, Duo, Okta activity, policy
monitoring, and detection engineering. Includes export/import,
drift detection, and version control workflows for dashboards.

---

### Other identity work

- [saml-metadata-parser](https://github.com/wesglockzin/saml-metadata-parser)
  — parse and debug SAML 2.0 metadata
- [okta-admin](https://github.com/wesglockzin/okta-admin)
  — Okta SAML/OIDC app inventory web UI
- [identity-llm-client](https://github.com/wesglockzin/identity-llm-client)
  — local LLM client (Ollama + Qwen 2.5 72B) for on-prem identity tools
- [personal-coworker-assistant](https://github.com/wesglockzin/personal-coworker-assistant)
  — local AI email and calendar triage with on-prem Exchange

---

### About these repos

Most of the work here is sanitized snapshots of internal tooling.
Commit histories reflect publication moments, not original development —
each repo is curated for public use rather than mirroring how the
internal version evolved. Internal identifiers are replaced with
placeholders (`your-username`, `your-org`, etc.) that you substitute
for your own environment.

---

### Stack

Python · Flask · Azure Container Apps · Okta · ADFS · Splunk · Duo ·
SAML 2.0 · OIDC · Ollama · on-prem LLMs

---

📫 wes.glockzin@gmail.com
