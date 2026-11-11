# Experimemo — Visual & Style Direction

## Presentation Principles
Exact adheres to the **"Write the web, ship the platform"** principle:
- **Layout is CSS's**: Flexbox, box-sizing, and standardized web geometry.
- **Presentation belongs to the platform**: Controls, system typography, system colors, and accessibility tokens align with host expectations (DOM on web, UIKit on iOS, AppKit on macOS).
- **Say less**: Structure the interface with semantic tags (`header`, `list`, `dialog`, `button`) and leave metric specifics to the platform's theme.

## Color Tokens & Theme
- Background: `-exact-secondary-background`
- Text: System label color
- Accents: System platform blue or custom brand tamber (`app.tamber`)

## Experimemo reference parity (2026-11-11)

For this project the user's explicit parity request takes precedence over the generic platform-default presentation above. Match the real Expo app at `F:/ReactNativeApps/experimemo` `origin/test` commit `23f39c3fb9c7a6780c0f18d3e5e3b74ae0f18d7b`: green primary `#299a0f`, light background/surface/text `#f8fafc` / `#e2e8f0` / `#111827`, dark background/surface/text `#09090b` / `#18181b` / `#f8fafc`, and secondary `#b85d13` light / `#d48a45` dark. Use the existing Yellowtail font asset for the Experimemo display title, readable system body type, green-bordered rounded cards, the reference spacing and system light/dark selection. The platform-blue/default-only direction above is not the acceptance target. Match screens and interaction states against the reference and record unavoidable platform differences. Exclude the experimental gesture card.
