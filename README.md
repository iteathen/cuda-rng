# cuda-rng

Reusable, application-neutral GPU random-generation semantics for the CUDA-JS ecosystem.

**Status:** architecture/governance bootstrap; production implementation not authorized.

CUDA-RNG is intended to own provider-neutral generator identity, deterministic stream/split/reproducibility rules, and finite distribution/sampling semantics. CUDA-JS remains the owner of CUDA runtime/provider mechanisms such as an eventual bounded cuRAND integration.

The repository deliberately does not own NN/search/graph/product policy for why randomness is used.

Start with `AGENTS.md`, `docs/PROJECT_CHARTER.md`, and `docs/decisions/ADR-0001-independent-rng-semantic-owner.md`.

Tracking:

- #1 ownership/bootstrap
- #2 repository controls/protected `main`
- #3 consumer-backed semantic roadmap

No package, public API, native provider, support, performance, or production-readiness claim exists yet.