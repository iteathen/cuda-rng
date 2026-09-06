# CUDA-RNG Status

**Updated:** 2026-09-05

**Architecture/governance:** independent RNG semantic owner integrated.

**Production implementation:** not authorized.

**Public API/package:** none.

**Native/provider support:** none claimed.

**Qualification:** governance only.

## Current work

- #1 established the durable ownership/bootstrap authority — completed.
- #2 tracks repository settings and protected-main alignment; `main` remains unprotected.
- #3 is the current consumer-backed RNG semantic activation roadmap; it is planning/assessment authority, not a production specification.

## Next executable decision

Assess concrete MCGS, NN and graph-analytics consumers and select the smallest reusable RNG semantic profile that survives consumer deletion. Any production implementation still requires an accepted bounded child specification and must consume only public lower-layer contracts.

CUDA-JS #92 remains the lower cuRAND provider/mechanism owner. Provider availability does not move generator/distribution/reproducibility meaning into CUDA-JS or authorize CUDA-RNG implementation by itself.

No roadmap entry, repository creation or completed governance bootstrap is production implementation authority.
