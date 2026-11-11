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

### Full parity with Experimemo on Expo (`origin/test` 23f39c3)

The existing Exact list is an incomplete prototype, not an accepted recreation. Match the reference app's screens, behavior, copy and visual style in the same states; ignore the temporary Software Mansion gesture card. Keep each item unchecked until its behavior and appearance are verified. Reference: `F:/ReactNativeApps/experimemo`, `project/todo.md`, `project/style.md`, `src/features`, `src/services`, `src/theme`, and `assets/`.

#### Foundation and visual system
- [ ] Inventory the reference at the pinned revision and capture comparable New, Track, editor, app-info and available onboarding screens in light/dark at phone and web widths, including populated and empty states. Record routes, interactions, field ordering, spacing, sizes, colors, typography, icons and assets; use these as acceptance references.
- [ ] Maintain a parity matrix linking each reference screen, action, state and data field to its source, Exact implementation, behavioral test and matching visual evidence; record exact copy, routes, native and web differences, intentional deviations and unsupported platform capabilities.
- [ ] Build the Exact app shell with New and Track navigation, info action, detail/back behavior, app-info modal, a not-found screen with a working Go home action, correct responsive layout, focus and browser navigation. Start at New as the reference does.
- [ ] Recreate the branded visual system: Yellowtail Experimemo display title, readable system body text, green accents and borders, neutral slate cards/backgrounds, rounded surfaces, spacing and system light/dark colors from the reference; include app icon and light/dark splash assets where supported.
- [ ] Resolve the Exact live web loop failure seen in this workspace (inspect-mode hook mismatch and repeated rebuilds); verify an edit rebuilds and reloads without changing unrelated source files.
- [ ] Verify Exact support and integration strategy for camera, photo library, local file ownership, custom fonts, theme and native targets at the pinned framework revision; record concrete gaps and implement or explicitly resolve them before claiming parity.
- [ ] Audit the existing Exact schema/list against the complete reference; replace the placeholder with production-capable data and UI. No fabricated claims of parity or completion.

#### Data and first-run behavior
- [ ] Implement an Exact-owned local experiment store for all reference fields (IDs, title, category, hypothesis, procedure, data plan, observations, dated results, notes, conclusion, planned photo count, photos, active/complete status and created/updated timestamps), including separate experiment and result photos, stable IDs and safe data migration/versioning.
- [ ] Seed both original labeled example experiments once into the same editable/deletable store as other records; preserve the full original seed values and order, and never recreate deleted examples on reload/reset.
- [ ] Implement create, list ordered by updated time, read by ID, update, status change, delete and reset with explicit loading/error handling and durable offline storage on supported Exact targets. Preserve user data through reload and launch; define photo ownership and handle unavailable files.

#### New experiment
- [ ] Recreate the New screen's Experimemo heading, subtitle, info action and cards in reference order: title, category, hypothesis, procedure, data collection plan, observations, field notes, conclusion and planned photo count.
- [ ] Match required title/hypothesis/procedure validation and messages, category default, nonnegative photo count, save/loading/error behavior, clear form after successful save, and navigate to Track. Do not lose entered data on failure.
- [ ] Match the New screen photo section: choose camera or photo library where supported, permission/cancel handling, image previews and attachment metadata; report unsupported capabilities honestly.

#### Track and experiment editor
- [ ] Recreate Track header and subtitle; show loading and original empty state with working Create experiment action; group active and completed records, ordered by update time, with matching section labels.
- [ ] Match each Track card: title, category and formatted updated date, status, hypothesis, observations fallback, latest result/count or empty message, first-photo preview/count, planned photo count and conclusion status. Make each card open the corresponding record.
- [ ] Recreate the detail/editor screen with record title, editable reference fields and 600 ms debounced autosave only when title and hypothesis are valid, with no save on initial load; include validation and safe error states; preserve changes across navigation and relaunch, and handle a missing/deleted record.
- [ ] Implement the active/complete toggle and its immediate persistence; Track must move records into the correct group.
- [ ] Implement multiple result entries automatically timestamped at save (date is not editable), newest first, with notes and photos: create a notes-or-photos result, edit notes, add/remove photos, confirm deletion, display date/time and update the Track summary; saving a result updates the editor draft and persists through autosave.
- [ ] Implement experiment-level camera/library photo add, preview and removal, including permissions, cancellation and accessibility. Verify real image availability after reopening, not just URI metadata.

#### App info and supporting screens
- [ ] Recreate the info modal's Settings, About and Feedback sections, developer/repository links and the reference support, terms and privacy URLs; return to the prior screen correctly.
- [ ] Implement its experiment deletion list including seeded examples, individual delete confirmation, reset-all confirmation, cancellation and post-delete/empty states. Each deletion is individual, and Reset returns to empty Track without silently restoring the examples.
- [ ] Port the URL-only privacy/terms and ready-to-start onboarding routes: two ephemeral acceptance switches enable Continue, and Open experiments returns to New. The reference never gates launch or persists these switches; do not introduce a mandatory gate or account.

#### Verification and tutorial
- [ ] Add meaningful data/Contract journeys for validation, both seed records, create → Track → edit → status → dated result/photos → delete/reset, missing record, cancellation, reload and failure cases, with camera/library testing on platforms that support them. Pin locale/time zone for formatted dates; verify New and editor have their distinct validation rules.
- [ ] Gate full-parity completion on that matrix: a list-only demo, disconnected save, missing persistence, absent photo flow or unverified screen must fail even when the build passes.
- [ ] Compare actual Expo and Exact screens side by side at matching sizes and light/dark settings; verify hierarchy, typography, colors, spacing, content, navigation, keyboard/screen reader use, large text and no clipping. Fix differences before claiming visual parity.
- [ ] Verify web first, then iOS simulator and other supported targets; explicitly document Exact limitations and Android availability. Test persistence, permissions and photos on each claimed target.
- [ ] Replace rejected V2 with an accepted parity slice containing the branded shell, tabs, both persisted seed records and Track, after matching the reference visually and functionally; keep V1 immutable. Update the scripted complete Infie/OpenAI/Claude tabs and completion messages from verified evidence; clicking tabs must show full conversations and agent handoffs returned to Infie. Do not represent simulations as real provider work.
- [ ] Distinguish reference parity from additional ideas: category exists as a field, but folders, search/filter and scientific-method controls are not established as working reference screens; track them separately as future work rather than claiming existing parity.

## Phase 3: Platform Hardening & Release
- [ ] Validate responsive layout on target devices (web and iOS simulator)
- [ ] Verify light and dark mode appearance
- [ ] Complete pre-release validation
