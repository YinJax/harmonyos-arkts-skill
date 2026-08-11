---
name: ark-ui
description: Implement or modify HarmonyOS ArkUI pages and components. Use for ArkTS UI layout, component composition, @State or observed state, navigation, lifecycle, rendering side effects, controllers, listeners, timers, and cleanup behavior.
---

# ArkTS UI

Keep UI behavior localized, predictable, and aligned with the project's existing ArkUI style.

## State

Choose the smallest owner that represents the user-visible fact.

| State | Owner |
| --- | --- |
| Local input, animation, temporary panel state | Component |
| Page coordination or navigation state | Page or existing ViewModel |
| Cross-page preference | Existing app storage or preference wrapper |
| Remote or persisted domain data | Service/repository plus the existing state owner |

Use the project's established decorators and state-management pattern. Do not introduce a second state system for one feature.

## Lifecycle

Register listeners, timers, location callbacks, controllers, and observers at the owner that can reliably remove them. Make initialization idempotent when a page or component can reappear. Dispose registrations when the owner disappears, and ignore async completions that no longer belong to the current view or request.

## Implement

1. Keep rendering and direct user interaction in components.
2. Put coordination, non-UI transitions, and business decisions in the existing ViewModel or manager layer.
3. Pass values and callbacks through the narrowest existing interface.
4. Preserve resource naming, imports, logging, error presentation, and component conventions.

## Done

Finish with changed UI files, state owner, lifecycle cleanup evidence, and whether `$ark-check` should run.
