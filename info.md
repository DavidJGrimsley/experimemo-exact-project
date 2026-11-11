# Experimemo

## Product Overview
Build an app for Scientists and people learning how to conduct experiments. Deliver a top class simple app that aids in experimentation without slowing work down.

- **Application Name**: Experimemo (id: `experimemo-exact`)
- **Framework**: Exact (upstream commit `9398d982e0`)
- **Template Starter**: blank
- **Application ID / Bundle**: `com.experimemo.app`
- **Target Platforms**: web

## Target Users
Scientists and people learning how to conduct experiments

## Problem Solved
There's no good way to track experiment data on the go.

## Product Goals
Provide a way for other scientists and I to track and manage our experiments effectively.

## Non-Goals
Ways to actually conduct experiments, analyze data, or collaborate with other scientists.

## First User Flow
Create an experiment

## Core Flows & Features
- Create an experiment
- Track multiple experiments, each with its own hypothesis, procedure, data collection, and results.
- View and edit existing experiments
- Add pictures and notes to experiments
- Organize experiments into folders or categories
- Search and filter experiments

## Screens
- New (create new experiment)
- Track (list of past experiments)
- App info modal

## Technical Architecture & Seam
- **View Layer**: Declarative Contract specification (`app.contract`)
- **Business & Data Logic**: TypeScript data provider (`app.ts`)
- **Persistence**: Exact local persistence / SQLite WASM
- **Testing & Verification**: Contract agent journeys (`app.test.contract`)
- **Development Toolchain**: Bun (>=1.4.2) and Rust (1.97.0); `bun exact.mjs web`

## Recorded Tech Stack & Platform Decisions
1. **Expo and NativeWind Discarded**: The original intake file in `project/info.original.md` specified Expo Router, NativeWindUI, EAS, and Expo SQLite. Per project directives, all Expo-specific and NativeWind instructions were ignored as generator commands. The app is implemented natively using Exact.
2. **Platform Strategy**: Original target platforms were `ios, android` with MVP `ios`. Exact natively supports web, macOS, iOS, Linux, and Windows. Web and iOS simulator serve as initial verification targets; Android support is experimental in Exact and deferred.
3. **Navigation & Modals**: Contract routes handle top-level screens (`Track`, `New`) and modal presentation handles `App info modal`.

## Source Provenance
- Source document: `F:/ReactNativeApps/experimemo/project/info.md` (sha256 `f8bfe8fbeb57570f2529aa96f0918e70f06b5818c29816242c049c9222a9b9d1`)
- Preserved verbatim in: `project/info.original.md`

