---
name: ark-scan
description: Inspect HarmonyOS Stage-model ArkTS projects before editing. Use when the user asks to analyze, plan, understand project structure, identify safe boundaries, avoid config or signing risk, or decide which HarmonyOS ArkTS command should handle the work.
---

# ArkTS Scan

Map the project before changing it. End with the smallest safe next action.

## Scan

1. Identify modules, entry abilities, page routing, source layout, resource layout, existing tests, and affected feature ownership.
2. Read only the live configuration needed for the request: SDK level, module declarations, permissions, dependencies, build tooling, signing, native/CMake, and lockfiles.
3. Trace the current call path before proposing a new manager, event channel, singleton, storage key, dependency, or cross-module abstraction.
4. Mark protected surfaces: signing, certificates, package identity, SDK compatibility, local device config, credentials, production constants, lockfiles, and generated build output.

## Route

| Finding | Next command |
| --- | --- |
| ArkUI page, component, state, navigation, or lifecycle | `$ark-ui` |
| ViewModel, service, repository, DTO, loading, cache, or async coordination | `$ark-flow` |
| Permission, file, persistence, network, WebView, native bridge, or device API | `$ark-kit` |
| Test, build, package, install, device validation, or release readiness | `$ark-check` |

## Deliver

Report the project boundary, the affected ownership path, protected surfaces, the chosen next command, and any user approval needed before configuration or device work.
