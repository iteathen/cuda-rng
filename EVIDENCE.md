# Evidence status

This repository follows the shared [iteathen evidence and validation policy](https://github.com/iteathen/.github/blob/main/EVIDENCE_POLICY.md).

## Current posture

CUDA-RNG is currently an architecture/planning repository. Its intended scope is documented, but there is no production implementation, installable package, public API, native-provider qualification, cryptographic-randomness claim, or performance claim.

## Registered claims

| Claim | Evidence class | Status |
| --- | --- | --- |
| `CUDA-RNG-PLAN-001` — intended scope: reusable random generation, deterministic streams, splitting, reproducibility, and bounded sampling through public CUDA-JS contracts | **UNVALIDATED** | planning hypothesis / project boundary |

The claim record is machine-readable in [`evidence/claims.json`](evidence/claims.json).

## What current evidence establishes

The repository establishes the current project boundary, planning state, architecture decisions, and reproducibility-oriented design intent.

## What it does not establish

It does not establish statistical quality, production reproducibility, native CUDA behavior, API stability, cryptographic suitability, performance, or external reproduction.

## Path to stronger evidence

When implementation is authorized, qualification should use deterministic reference vectors, statistical suites where appropriate, exact seed/stream provenance, and hardware measurements for native paths.

## Non-mutation rule

Evidence work may inspect, test, benchmark, and document CUDA-RNG. It must not change substantive operational behavior merely to make an evidence claim pass.
