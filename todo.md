# Experimemo — Implementation Roadmap

## Phase 1: Greenfield Setup & Verification
- [x] Scaffold initial Exact application structure (`blank`)
- [x] Run initial smoke test via `bun exact.mjs test web`
- [x] Verify Contract compilation via `bun exact.mjs contract build`
  - Verified: `bun exact.mjs contract build app.contract --json --errors-only` (exit 0; no errors).

## Phase 2: Core Experiment Feature Implementation
- [ ] Define Experiment data schema in `app.ts`
- [ ] Implement Experiment List view in `app.contract`
- [ ] Implement Create Experiment form and validation in `app.contract`
- [ ] Add functional unit and Contract agent tests in `app.test.contract`

## Phase 3: Platform Hardening & Release
- [ ] Validate responsive layout on target devices (web and iOS simulator)
- [ ] Verify light and dark mode appearance
- [ ] Complete pre-release validation
