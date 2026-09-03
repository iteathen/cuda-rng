# ADR-0001: Independent RNG Semantic Owner

**Status:** Accepted

**Date:** 2026-09-02

## Context

CUDA-JS already has a deferred cuRAND provider/mechanism roadmap, while materially different consumers such as CUDA-MCGS, CUDA-NN and graph analytics may need randomness for different reasons. Seed/reproducibility/distribution meaning should not become CUDA runtime vocabulary or be duplicated separately in each consumer.

## Decision

`cuda-rng` is the independent owner for reusable provider-neutral RNG semantics. It depends downward on public CUDA-JS mechanisms and has no reverse dependency.

CUDA-JS retains native provider discovery/handles, memory/views, operation lifecycle, compilation and cleanup. Consumers retain policy for why/when random values affect search, training, graph algorithms or products.

## Deletion test

Deleting any one consumer must leave CUDA-RNG coherent. Deleting CUDA-RNG must leave CUDA-JS coherent as a generic runtime. A semantic contract that requires one consumer's vocabulary does not belong here.

## Implementation gate

Repository existence creates no API. Issue #3 must select a bounded reusable profile from concrete consumers, followed by an accepted specification and independent reference evidence.

## Consequences

- cuRAND remains a mechanism/provider concern rather than the public semantic authority.
- reproducibility/distribution semantics have one reusable home.
- consumer-specific stochastic policy remains outside this repository.
- missing generic GPU mechanisms route to CUDA-JS rather than creating a native escape path.

## Non-goals

Cryptographic randomness, arbitrary provider passthrough, immediate implementation, or provider-independent sequence guarantees not supported by accepted evidence.