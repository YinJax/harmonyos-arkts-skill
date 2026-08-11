---
name: ark
description: Route HarmonyOS Stage-model ArkTS work to focused command skills. Use for broad HarmonyOS or ArkTS requests, unclear project tasks, or when choosing between project scanning, ArkUI UI/state work, layered async business flows, platform capabilities, and verification.
---

# HarmonyOS ArkTS Skill

Use this as the command router for HarmonyOS / ArkTS projects. Pick the smallest command that matches the user's request, then follow that command instead of carrying the whole workflow.

## Commands

| Command | Use when | Outcome |
| --- | --- | --- |
| `$ark-scan` | The request is broad, risky, or needs project context before editing. | Project shape, ownership boundary, protected surfaces, and next command. |
| `$ark-ui` | ArkUI page, component, state, layout, navigation, or lifecycle behavior is involved. | Localized UI change with one state owner and clear cleanup. |
| `$ark-flow` | ViewModel, service, repository, DTO, loading, error, cache, or async coordination is involved. | A readable component-to-service flow with pending, success, and failure paths. |
| `$ark-kit` | Permission, file, storage, network, WebView, native bridge, MapKit, GNSS, Bluetooth, media, or device API is involved. | Capability integration behind the existing boundary with authorization and error handling. |
| `$ark-check` | The user asks how to test, build, package, install, review, or validate a HarmonyOS change. | Risk-proportionate verification evidence and remaining runtime risk. |

## Routing Rules

1. If the request says "analyze", "inspect", "before changing", "safe boundary", or the affected files are unclear, start with `$ark-scan`.
2. If the user asks for a concrete UI or state change, use `$ark-ui`; add `$ark-flow` only when data or business coordination crosses the component boundary.
3. If the change touches permissions, files, persistence, networking, hardware, WebView, native code, or platform Kits, use `$ark-kit`.
4. If the user asks for checks or after any non-trivial change, finish with `$ark-check`.
5. If a command exposes a configuration change, signing surface, SDK change, dependency, lockfile, or device action, state the impact and wait for explicit user scope before editing or running that surface.

## Shared Boundary

Use the target project as the source of truth. Preserve its working architecture and use official HarmonyOS APIs when the project does not already establish a compatible pattern. Keep each change inside the existing module, page, ViewModel, service, adapter, or repository boundary unless the user explicitly asks for a broader refactor.

## Scope

These commands provide reusable HarmonyOS engineering workflow. Do not encode product domain rules, proprietary data formats, device-specific constants, local paths, release steps, credentials, certificates, or signing material.
