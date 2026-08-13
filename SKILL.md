---
name: ark
description: Route HarmonyOS Stage-model ArkTS work through project inspection, official-document evidence, DevEco command discovery, safe implementation boundaries, and risk-proportionate verification. Use for broad ArkTS tasks or when deciding whether to scan, change ArkUI, coordinate async flow, integrate a system Kit, or verify a change.
---

# Ark

Route HarmonyOS / ArkTS work to the smallest command. This skill is the control layer: the target project supplies local facts, the official documentation lookup supplies platform facts, and DevEco CLI supplies execution evidence.

## Evidence Profile

Assign each task the highest evidence level that affects the decision:

| Profile | Use when | Required action |
| --- | --- | --- |
| `local` | Pure ArkTS/UI/resource change inside known boundaries. | Inspect the current project path and produce the changed boundary. |
| `doc-bound` | Platform API, Kit, permission, API level, error code, or compatibility matters. | Use the official-document lookup and record the constraint that changes the decision. |
| `config-bound` | `module.json5`, SDK, dependency, native build, signing, package identity, lockfile, or build tooling may change. | Show the smallest config diff and ask for explicit approval before editing. |
| `runtime-bound` | Build, package, install, emulator/device, external service, logs, location, rendering, or hardware capability must be observed. | Discover the project command/check first; run only the user-authorized scope and report the exact result. |

Do not copy platform API catalogs, fixed SDK paths, device identifiers, certificates, or static DevEco command lines into this skill. The project, official docs, and current environment are the sources of truth.

## Commands

| Command | Use when | Required deliverable |
| --- | --- | --- |
| `$ark-scan` | Scope, ownership, evidence profile, or safety boundary is unclear. | Project change map and safe next command. |
| `$ark-ui` | ArkUI page, component, state, navigation, or lifecycle changes. | State/lifecycle ledger and changed UI boundary. |
| `$ark-flow` | ViewModel, service, repository, DTO, cache, loading, or async coordination changes. | Async contract from user action to data source. |
| `$ark-kit` | Permission, file, storage, network, WebView, native bridge, MapKit, GNSS, Bluetooth, media, or device API changes. | Capability contract with official constraint and failure behavior. |
| `$ark-check` | Tests, builds, packaging, installation, device checks, logs, or review evidence is requested. | Verification manifest with evidence, failures, and remaining risk. |

## Routing Rules

1. Start with `$ark-scan` when affected files, module ownership, call path, evidence profile, or protected configuration are unknown.
2. Use `$ark-ui` for local UI/state/lifecycle work; add `$ark-flow` when data or business coordination crosses the component boundary.
3. Use `$ark-kit` for platform capabilities, permissions, system APIs, and configuration implications.
4. Finish every non-trivial authorized change with `$ark-check`.
5. When `$ark-check` fails, route by the failing evidence: UI/lifecycle to `$ark-ui`, async/data to `$ark-flow`, platform/config/device to `$ark-kit`, unknown ownership to `$ark-scan`.

## Approval Boundaries

Require explicit user approval before editing signing, certificates, package identity, SDK compatibility, dependencies, lockfiles, permissions, native build surfaces, generated output, device state, or production constants.

## Shared Boundary

Preserve the project's existing module, page, ViewModel, service, adapter, repository, resource, logging, and error-presentation boundaries. Prefer the official API and the project's compatible existing pattern. Keep reusable workflow guidance here; keep credentials, certificates, local paths, device identifiers, and product-domain rules in the target project.
