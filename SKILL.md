---
name: arkts-project-skill
description: Implement or modify HarmonyOS Stage-model ArkTS projects. Use when requests involve ArkUI pages or components, state or lifecycle behavior, ViewModel or service flows, permissions, data persistence, files, networking, system capabilities, native bridges, tests, builds, or device verification.
---

# ArkTS Project Skill

Use the target project as the source of truth. Preserve its working architecture and use official HarmonyOS APIs when the project does not already establish a compatible pattern.

## Start With The Project

1. Identify the application modules, entry abilities, page routing, source layout, resource layout, existing tests, and the APIs already used by the affected feature.
2. Read the live configuration only when the request depends on it. Use the project's SDK level, module declarations, dependencies, and build tooling rather than assumptions from another HarmonyOS project.
3. Keep the change in the existing ownership boundary. Prefer a small extension of a component, ViewModel, manager, service, or adapter over a new cross-cutting framework.

### Configuration Boundary

Treat application code and project configuration differently. If the requested behavior requires a change to permissions, dependencies, signing, package identity, SDK compatibility, Hvigor/CMake setup, or a lockfile, state the exact required change and its impact before editing that surface. Proceed only when the user explicitly includes that configuration change in scope.

## Route The Request

| Request shape | Read | Deliver |
| --- | --- | --- |
| ArkUI page, component, state, layout, or lifecycle | [references/arkui-and-architecture.md](references/arkui-and-architecture.md) | A localized UI change with clear state ownership and cleanup |
| Business flow, loading, navigation, or data coordination | [references/arkui-and-architecture.md](references/arkui-and-architecture.md) | A clear component-to-service flow with observable loading and failure states |
| Permission, file, persistence, database, network, or device API | [references/platform-capabilities.md](references/platform-capabilities.md) | An API integration that handles availability, authorization, and errors |
| MapKit, GNSS, Bluetooth, NAPI/C++, media, or another specialized capability | [references/platform-capabilities.md](references/platform-capabilities.md) | An extension of the existing adapter boundary, not a new default dependency |
| Test, compilation, packaging, install, or device validation | [references/verification.md](references/verification.md) | Risk-proportionate verification with clear pass/fail evidence |

## Implement

1. Trace the current call path before adding another manager, event channel, singleton, or storage key.
2. Give every mutable state value one owner. Pass values and callbacks through the narrowest existing interface; do not create parallel state for the same user-visible fact.
3. Model asynchronous work with an explicit pending, success, and failure outcome when the user can observe the operation. Ignore stale completions after the owner has changed or disappeared.
4. Preserve the project's resource naming, imports, logging, error handling, and test conventions. Add an abstraction only when it removes a real dependency or repeated complexity.
5. Treat system APIs and native code as capability boundaries. Validate inputs and translate platform failures into the application's existing error model.

## Verify And Report

1. Run the smallest relevant static check or existing test first. Expand to build, package, install, or device verification only when the user requests it or the risk requires it.
2. Report changed files, the user-visible result, evidence that was run, and any verification that remains unrun. Do not claim runtime or device behavior from static inspection alone.
3. When an external capability is unavailable, report the precise boundary and leave the project in a recoverable state.

## Scope

This skill provides reusable HarmonyOS engineering workflow. Do not encode product domain rules, proprietary data formats, device-specific constants, local paths, release steps, credentials, certificates, or signing material. Keep MapKit, GNSS, offline maps, NAPI, Bluetooth, and media support conditional on actual use in the target project.
