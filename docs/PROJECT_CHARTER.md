# CUDA-RNG Project Charter

**Status:** Accepted architecture after bootstrap integration; production implementation not authorized.

## Purpose

Provide reusable, application-neutral stochastic generator and distribution semantics above public CUDA-JS contracts without making CUDA-JS an RNG framework and without absorbing consumer policy.

## CUDA-RNG owns, when separately accepted

- provider-neutral generator/profile identity;
- seed, sequence, offset/subsequence and deterministic split/fork semantics;
- reproducibility and explicit state-transition rules;
- finite distribution/sampling contracts;
- bounded generation plans and RNG-specific numerical/statistical conformance;
- serialization/checkpoint meaning for RNG state only if independently justified.

## CUDA-RNG does not own

CUDA Driver/runtime/compiler/memory/views/operations/provider handles or native cuRAND lifecycle; generic Tensor mathematics; NN initialization/dropout/training-state policy; MCGS exploration/search policy; graph-algorithm semantics; cryptographic randomness; or downstream product meaning.

## Dependency direction

`cuda-rng -> public cuda-js`.

Tensor, NN, MCGS, graph analytics and products may consume CUDA-RNG optionally while retaining the semantic reason randomness is used. CUDA-JS remains coherent if CUDA-RNG is deleted.

## Provider boundary

A CUDA-JS cuRAND/provider primitive may expose the bounded native mechanism needed to realize an accepted RNG plan. CUDA-RNG owns provider-neutral reproducibility/distribution meaning and must not expose raw native state structs/options merely to mirror cuRAND.

## Activation gate

Issue #3 must compare concrete consumers and identify a smallest reusable semantic profile. Production source/API requires an accepted specification and independent reference evidence. A conclusion that a consumer can use a lower provider directly without reusable CUDA-RNG semantics is valid.

## Resource/lifecycle rule

Every accepted generator/state/plan is finite with one owner, identity, borrowing rules, bounds, failure and terminal disposition. Garbage collection is not authoritative release for scarce lower-layer resources.

## Non-goals

Cryptographic RNG, universal distribution breadth, cross-provider byte-for-byte promises without evidence, consumer policy, or native/provider implementation in this repository.