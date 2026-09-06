# CUDA-RNG Agent Entry Point

Read this file before changing the repository.

## Authority order

1. Explicit current project-owner instruction.
2. This file.
3. Accepted ADRs under `docs/decisions/`.
4. Accepted specifications under `docs/specs/`.
5. `docs/PROJECT_CHARTER.md`.
6. Status/roadmap/issues, which organize work but are not implementation authority.

## Required method

For every meaningful unit of work use:

`assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document`

Do not implement from an issue title, roadmap row, provider API, or prior-agent conclusion without proving the natural owner and accepted contract first.

## Design hierarchy

`LEGO -> SOLID -> CUPID -> KISS`

LEGO is the outer architecture rule: ownership, universality, replaceability, scope containment, damage-limiting encapsulation, and context containment. A LEGO is too large when one agent cannot hold its complete authoritative working set—contract, implementation, invariants, lifecycle/resource/failure rules, tests/conformance, and immediate dependency/consumer interfaces—in focused attention with substantial headroom for reasoning and review. Context fit is a first-class boundary criterion alongside semantic, lifecycle, resource/failure, substitution, and change cohesion. When exceeded, recursively split at the strongest real seam or narrow scope; do not create arbitrary modules that duplicate truth or require cross-boundary internal knowledge.

Inside a valid LEGO, SOLID structures responsibilities and dependency direction, CUPID shapes the implementation, and KISS removes remaining unjustified complexity. A lower-level principle may not defeat a higher-level one.

One semantic fact/resource/lifecycle has one visible owner. First-consumer convenience is not ownership proof.

## Repository boundary

CUDA-RNG owns reusable provider-neutral stochastic generator/distribution semantics only when separately accepted: generator/profile identity, seed/sequence/offset/subsequence and deterministic split/fork meaning, reproducibility/state-transition rules, finite distribution/sampling semantics, and RNG-specific conformance.

CUDA-RNG does not own CUDA Driver/runtime/compiler/memory/view/operation/provider lifecycle, native cuRAND handles/state structs, Tensor mathematics, NN dropout/initializer/training policy, MCGS exploration/search policy, graph-algorithm meaning, cryptographic randomness, or downstream product semantics.

Dependency direction is `cuda-rng -> public cuda-js`. Consumers may optionally depend on CUDA-RNG; CUDA-JS never depends on CUDA-RNG.

## Lower-layer escalation

A need for direct native code, FFI, CUDA C++, PTX, private CUDA-JS imports, provider handles, or duplicated memory/operation/provider lifecycle is evidence of a lower-layer gap. Stop and assess CUDA-JS ownership rather than creating a workaround here.

CUDA-JS issue #92 remains the cuRAND provider/mechanism tracker. CUDA-RNG owns the reusable semantics above such mechanisms, not the binding itself.

## Source and language

Maintained production/tooling code, when eventually authorized, is JavaScript/ESM plus accepted restricted Device-JS through public lower-layer contracts. Do not add Python, maintained C/C++, CUDA C++, hand PTX, direct FFI/Driver access, or subprocess-native implementations without an explicit successor architecture decision.

## Current gate

Repository creation and this bootstrap do not authorize production source or API. Issue #3 is the consumer-backed activation roadmap. A bounded accepted specification is required before implementation. Issue #2 separately owns GitHub repository controls/protected-main alignment.

## Completion rule

Completion requires exact-effect review, relevant qualification, cleanup, honest claim limits, and contradiction-free authority. Mocks/portable evidence never prove native/provider/performance support.