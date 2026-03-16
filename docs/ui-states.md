# Orivon UI State Logic (v1)

This document defines how the Orivon client renders security states based on the WSEO scoring payload.

The backend returns the following payload fields:

- Score_Int
- Reason_Code_Hash
- Timestamp

Example payload:

{
  "Score_Int": 82,
  "Reason_Code_Hash": "0xA91F",
  "Timestamp": 1710000000
}

---

## Tier Mapping

| Score Range | Tier  | UI Behaviour |
|--------------|-------|--------------|
| 70–100 | GREEN | Safe interaction |
| 40–69 | AMBER | Warning displayed |
| 0–39 | RED | High-friction confirmation |

---

## GREEN State

User sees:

Safe interaction indicator

UI behaviour:

- Show green trust indicator
- Allow interaction normally
- Display optional explanation from Reason_Code

---

## AMBER State

User sees:

Warning message

UI behaviour:

- Show amber warning indicator
- Display explanation message
- Allow interaction without friction

---

## RED State

User sees:

High risk warning

UI behaviour:

- Show red warning screen
- Display explanation message
- Require explicit confirmation

Example friction flow:

User must type:

"I understand the risks"

or wait through a short countdown before continuing.

---

## Design Principle

Orivon does **not block users**.

The system provides information and friction but preserves user self-custody.
