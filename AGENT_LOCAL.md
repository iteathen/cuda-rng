# Repository context: cuda-rng

Universal engineering and design guidance comes from the account-global `AGENTS.md`.

## Mission and ownership

CUDA-RNG owns reusable provider-neutral stochastic generator/distribution semantics when accepted: generator/profile identity, seed/sequence/offset/subsequence and split/fork meaning, reproducibility/state transitions, finite sampling semantics, and RNG conformance.

CUDA-JS owns CUDA/provider mechanisms. Tensor, NN, MCGS, cryptographic randomness, and product policy remain with their natural owners.

## Local routing

Accepted `docs/decisions/`, `docs/specs/`, repository status/roadmap, and current issues own local implementation/activation truth.

## Local constraints

Dependency direction is `cuda-rng -> public cuda-js`. Maintained code uses JavaScript/ESM plus accepted Device-JS through public lower contracts; no Python, direct native FFI/CUDA implementation, hand PTX, or private CUDA-JS imports.