# ArkUI And Architecture

## State Ownership

Choose the smallest owner that represents the user-visible fact.

| State | Owner | Pass Down As |
| --- | --- | --- |
| Local input, animation, temporary panel state | Component | `@State` or existing local pattern |
| Page coordination or navigation state | Page or its ViewModel | Explicit input, callback, or existing shared model |
| Cross-page preference | Existing application storage or preference wrapper | A single named key and access boundary |
| Remote or persisted domain data | Service/repository plus the existing state owner | Result model, not duplicated mutable copies |

Use the project's established decorator and state-management pattern. Do not introduce a second state system solely for one feature.

## Lifecycle

Register listeners, timers, location callbacks, controllers, and observers at the owner that can reliably remove them. Make initialization idempotent when a page or component can reappear. Dispose registrations when the owner disappears, and ignore asynchronous completions that no longer belong to the current view or request.

## Component Boundaries

Keep rendering and direct user interaction in components. Put coordination, non-UI state transitions, and business decisions in the existing ViewModel or manager layer. Put storage, parsing, and platform I/O behind services or adapters. Follow a local pattern when one exists; do not perform a broad reorganization as part of a feature request.

## Async Flow

For work visible to the user, make the flow legible:

1. Start from one owner and set the pending state.
2. Call the existing service or adapter.
3. Apply success only if the request is still current.
4. Surface failure through the project's existing message or error state.
5. Clear pending state on every terminal outcome.

Avoid hiding errors in logs when the user needs an action, and avoid showing raw platform error details in the UI when the project already has a safer message convention.
