# CUDA-RNG Status

**Architecture:** independent RNG semantic owner selected.

**Production implementation:** not authorized.

**Public API/package:** none.

**Native/provider support:** none claimed.

**Qualification:** governance only.

## Current work

- #1 establishes the durable ownership/bootstrap authority.
- #2 tracks repository settings and protected-main alignment; `main` is unprotected at bootstrap.
- #3 is the consumer-backed RNG semantic activation roadmap.

The first implementation must be justified by a reusable consumer need, accepted through a bounded specification, and must consume only public lower-layer contracts. CUDA-JS #92 remains the lower cuRAND provider/mechanism owner.

No repository creation or roadmap entry is implementation authority.