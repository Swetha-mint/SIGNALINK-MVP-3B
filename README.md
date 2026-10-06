# SIGNALINK MVP-3B — Fault-Tolerant Communication Recovery

A deterministic software test space for communication-state recovery when an invalid or corrupted event appears.

## Objective
Protect the communication state from a bad token or dropped/corrupted input.

## Test
Inject:
- HELLO / YES / STOP → accepted events
- NOISE → treated as an invalid token and ignored

The register retains the valid event sequence instead of allowing the invalid token to corrupt it.

## Engineering interpretation
This is a small finite-state-machine recovery baseline. It is deliberately deterministic rather than pretending that a tiny browser demo is already a statistical Markov model or production ECC engine.

Future work can add formal Hamming/ECC logic, frame checks, sensor confidence, and hardware fault injection.

Theory → Build → Measure → Explain → Hardware
