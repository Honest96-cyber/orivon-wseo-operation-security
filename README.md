# Orivon × WSEO Operation Security Integration

This repository contains the reference specification and integration work for **Operation Security (Layer 2)** within the Orivon ecosystem, powered by the **WSEO oracle engine**.

The goal is to provide **pre-signature safety analysis** for blockchain transactions so users can understand the risks of an operation before approving it.

---

## Architecture

Orivon security is divided into two layers.

### Layer 1 — Platform Security (Orivon)

Handled by the Orivon runtime.

Includes:
- WASM sandboxing
- secure execution environment
- capability boundaries

### Layer 2 — Operation Security (WSEO)

Evaluates the **specific operation the user is about to sign**.

The WSEO oracle engine analyzes on-chain parameters and returns a deterministic score describing the safety of the transaction.

---

## Output Format

WSEO returns:

- `score_int` (0–100)
- `tier` (GREEN | AMBER | RED)
- `reason_code_hash`
- `timestamp`

Example payload:

{
  "score_int": 92,
  "tier": "GREEN",
  "reason_code_hash": "0xabc123",
  "timestamp": 1716239021
}

The Orivon UI renders **tier-based warnings** to users.

---

## Risk Pillars (v1)

The scoring model focuses on the most common DeFi loss vectors:

1. Unlimited approvals  
2. Contract mutability & admin privileges  
3. Code authenticity / audit status  
4. Irreversible actions / lockups

---

## Status

v1 specification is being finalized and integration testing will begin with mock payloads.
