# CUDA-RNG Status

**Updated:** 2026-09-06

**Architecture/ownership:** accepted independent RNG semantic owner under SPEC-0001.

**Production implementation:** not authorized.

**Public API/package:** none.

**Native/provider support:** none claimed.

## Current work

- #1 ownership/bootstrap authority — completed.
- #2 repository-control/protected-main alignment — completed; `main` is protected and the selected CUDA-family settings were read back.
- #3 is the current consumer-backed RNG semantic activation roadmap; it remains planning/assessment authority, not a production specification.

## Next executable decision

Assess concrete CUDA-MCGS and graph-analytics consumers and select the smallest reusable RNG semantic profile that survives consumer deletion. A future NN consumer counts only if `cuda-nn` is independently reactivated by new reusable-semantic evidence. Production implementation still requires an accepted bounded child specification and public lower-layer contracts.

CUDA-JS #92 is historical/dormant cuRAND native-provider provenance, currently closed `not_planned`; it is not an active dependency. If an accepted CUDA-RNG profile later selects cuRAND, reactivate that lower mechanism or select the smallest bounded CUDA-JS successor.

Generic algorithm semantics do not move into CUDA-JS merely because multiple GPU consumers need them. Any independently reusable non-native algorithm layer requires a JavaScript/TypeScript owner above CUDA-JS.

## Governance

Protected-main and repository-setting alignment is complete. No local CI workflow currently exists, so no required status-check name is fabricated.

No roadmap entry, provider availability, repository creation or completed governance bootstrap is production implementation authority.
