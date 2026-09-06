# SPEC-0001: Native Boundary and JavaScript/TypeScript Implementation

**Status:** Accepted architecture/ownership authority; production RNG profiles remain separately gated.

**Version:** 1.0.0

**Owner:** CUDA-RNG

**Lower authority:** `iteathen/CUDA-JS` SPEC-0032

## Purpose

CUDA-RNG owns reusable provider-neutral RNG, distribution, sequence, reproducibility and sampling semantics. CUDA-JS is the sole native CUDA/provider integration owner.

## Repository implementation rule

Maintained CUDA-RNG source is JavaScript/TypeScript. Restricted Device-JS generation is permitted only through public CUDA-JS contracts.

CUDA-RNG does not maintain C, C++, CUDA C++, PTX, direct native FFI, native addons, cuRAND bindings, native handles/pointers, ABI structs or platform discovery code. Native evidence may be produced externally and recorded, but native oracle/provider source is not maintained here.

A missing native mechanism routes to CUDA-JS before any local workaround.

## CUDA-RNG owns

- generator/profile meaning independent of provider;
- seed/sequence/subsequence/offset/fork/split semantics;
- distribution and sampling semantics;
- reproducibility/equivalence guarantees and their limits;
- RNG-specific finite state/resource policy;
- provider-selection/fallback policy at the RNG semantic boundary;
- JavaScript/TypeScript reference and conformance evidence.

## CUDA-JS owns

- native cuRAND or other provider discovery/ABI/resources if selected;
- native generator/device-header/resource mechanisms;
- allocations/views/operations/compiler artifacts;
- native provider errors, compatibility and teardown.

CUDA-RNG may consume a public provider mechanism but never owns the native provider handle or calls it directly.

## Memory and execution policy

RNG-specific state lifetime, stream association or reproducibility constraints remain CUDA-RNG semantics. Generic allocation, stream, operation, graph, managed/peer memory and physical-memory mechanisms remain CUDA-JS-owned. Cross-domain memory-management strategy requires its own JavaScript/TypeScript owner if independently justified.

## Activation gate preservation

This specification does not select a generator, distribution or provider and does not authorize production RNG implementation merely because the native boundary is defined.

## Non-goals

No native RNG backend, no arbitrary cuRAND passthrough, no CUDA-JS semantic expansion, no production capability or support claim.
