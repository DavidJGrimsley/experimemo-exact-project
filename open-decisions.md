# Open decisions

Recorded at generation from reviewed inputs. The generator did not resolve these; the owner decides them before implementation.

Source: `F:/ReactNativeApps/experimemo/project/info.md` (sha256 f8bfe8fbeb57570f2529aa96f0918e70f06b5818c29816242c049c9222a9b9d1), read-only.

- [ ] Platform Decision: The original specification requested ios and android (MVP ios). In Exact, web and iOS are first-class native hosts; Android support is experimental in Exact and deferred for the MVP. Generated with web and iOS target platforms.
- [ ] Technology Stack Decision: All Expo, Expo Router, NativeWindUI, EAS, and Expo SQLite directives from F:/ReactNativeApps/experimemo/project/info.md are ignored per project instructions. Experimemo is implemented natively using Exact (declarative app.contract view seam and TypeScript app.ts data provider).
- [ ] Navigation & Screens Decision: The original intake document contained contradictory navigation notes (Native tabs + modal stack vs Drawer + Tabs) and screen listings (App info modal vs Settings). For Exact, navigation is modeled via Contract routes (Track and New) with a modal dialog for App info. Settings and drawer navigation remain deferred.
- [ ] Persistence Strategy: Replaced Expo SQLite with Exact local storage / SQLite WASM for offline experiment data.
