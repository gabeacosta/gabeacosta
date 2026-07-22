# Gabe Acosta

**I build and operate production infrastructure for AI agents.**

Verification, MCP governance, runtime reliability, voice-agent orchestration, multi-tenant data, and cost-aware inference — the layer that keeps autonomous agents observable, testable, and operationally sane. Most of what's here was extracted from systems I run in production, not written as demos.

Working doctrine: **logs are telemetry, receipts are evidence** — and **`ran ≠ succeeded, wired ≠ live`.**

---

### Start here

| Repository | What it demonstrates |
|---|---|
| **[agentreceipts](https://github.com/gabeacosta/agentreceipts)** | Ed25519-signed, offline-verifiable receipts for any LLM/agent call — local-only, secret-scrubbed |
| **[governed-mcp-spine](https://github.com/gabeacosta/governed-mcp-spine)** | Pre-execution capability authorization, write-scope enforcement, hash-chained tamper-evident audit |
| **[clue-runtime](https://github.com/gabeacosta/clue-runtime)** | Runtime reliability — dependency-honest health checks and startup drift fingerprinting |
| **[voxmaestro](https://github.com/gabeacosta/voxmaestro)** | Vendor-independent voice-agent orchestration — declarative state machine, tool bridge, handoff protocol |
| **[agentic-crm-os](https://github.com/gabeacosta/agentic-crm-os)** | Concurrent, auditable workflow state — `FOR UPDATE` row locking against lost updates |
| **[mcp-audit-plugin](https://github.com/gabeacosta/mcp-audit-plugin)** | MCP config auditing for Claude Code — finds the prompt-cache/tool-ordering cost bug with a one-line fix |

Cost-aware routing lives in **[smart-ai-router](https://github.com/gabeacosta/smart-ai-router)**. Case studies and receipt-backed proof artifacts are in **[ai-portfolio](https://github.com/gabeacosta/ai-portfolio)**.

---

### Selected incidents & lessons

Real operational failures I root-caused and then designed against:

- **Silent health check.** A service reported `healthy` for six days while its database dependency was unavailable → `clue-runtime`'s dependency-aware health and drift detection.
- **Fail-open by default.** Found an HMAC verification path that defaulted to *open* across 12 call sites in the MCP control layer → closed it and the surrounding security findings.
- **Wired ≠ live.** An observability pipeline never ingested a single trace from the day it deployed — a hardcoded address had drifted after an earlier incident. The dashboard was green the whole time.

---

### Stack

Go and Python services · MCP · n8n workflow orchestration · Qdrant / PostgreSQL / Redis · local inference (Ollama / MLX / llama.cpp) · Docker + Traefik on a self-run VPS control plane · Tailscale mesh.

---

### Public vs private

These repositories are independently usable components extracted from larger production systems. The orchestration control plane, business workflows, and customer-facing products are private. Happy to walk through architecture and the private work in a conversation.

### Current focus

Verifiable execution governance for coding agents — independent verification of review state, diff scope, CI provenance, and operator approval before an agent can claim a task is done.

### Contact

<!-- fill: email · LinkedIn · site -->
[ gabriel@gentic.pro ] · [ LinkedIn ] · [ site ]
