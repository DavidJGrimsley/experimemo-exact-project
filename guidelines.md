# Experimemo — Engineering Guidelines

## Exact Framework Rules
1. **Toolchain**: Use Bun (pinned 1.4.2 recommended) and Rust (1.97.0) for execution and tests. Node/npm are not used for Exact runtime.
2. **Commands**:
   - Web development loop: `bun exact.mjs web`
   - Automated test suite: `bun exact.mjs test web`
   - Contract compilation gate: `bun exact.mjs contract build app.contract --json --errors-only`
   - Native builds (where supported): `bun exact.mjs run`
3. **Seam Safety**:
   - Keep view logic in `app.contract`.
   - Keep business logic and data providers in `app.ts`.
   - Never run Expo Doctor on an Exact project; Exact diagnostics belong to Exact.
4. **Agent Testing**:
   - Write automated user journeys in `app.test.contract`.
   - Verify all tests pass before completing development milestones.

<!-- MDS_CONTROL_PLANE_CONTRACT -->

## Workspace Control-Plane Contract

- This control repository `project/` directory is the only canonical human-readable project memory for an initialized workspace.
- Checkout-local legacy `project/` directories are read-only migration inputs; agents must not create, update, or regenerate planning files there.
- The UD may edit `todo.md` directly. Agents make narrow edits only and never replace or regenerate the entire file.
- Task agents return structured findings to Infie. Infie is the sole writer for shared human-readable project memory.
- Before a shared-memory update, Infie refreshes the control repository. Approved edits use a dedicated branch, push, and PR; direct main pushes are bootstrap or UD-authorized merge actions only.
- I² clients read the control repository default branch and use the same PR workflow. Keep agent-private coordination state outside project-memory Markdown.
