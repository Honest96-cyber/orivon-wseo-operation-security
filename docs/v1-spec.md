# Operation Security v1 Specification

This document defines the initial specification for Operation Security integration between Orivon and the WSEO oracle engine.

## Output Contract

WSEO returns:

- score_int
- tier
- reason_code_hash
- timestamp

## Tier Definitions

### GREEN
Low risk operation.

### AMBER
Moderate risk or uncertainty.

### RED
High risk operation requiring explicit acknowledgement.

## Pillars

The scoring rubric evaluates four core vectors:

- Unlimited approvals
- Contract mutability
- Code authenticity
- Irreversible lockups

Further scoring logic is handled by the WSEO engine.
