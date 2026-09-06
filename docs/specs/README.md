# CUDA-RNG specifications

**Architecture/ownership authority is accepted; no production RNG capability specification is accepted yet.**

- [`SPEC-0001-native-boundary-and-js-only-implementation.md`](SPEC-0001-native-boundary-and-js-only-implementation.md) — accepted cross-cutting rule that CUDA-RNG remains JavaScript/TypeScript, CUDA-JS owns native CUDA/provider integration, and provider-neutral RNG semantics remain here. This specification does not select or authorize a generator/provider profile.

The [activation roadmap](https://github.com/iteathen/cuda-rng/issues/3) organizes assessment. Production implementation must first have a bounded, consumer-backed semantic contract accepted under the [development instructions](../../AGENTS.md).

Start with the [project charter](../PROJECT_CHARTER.md) and [architecture decision](../decisions/README.md) to understand the intended scope.
