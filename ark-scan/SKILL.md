---
name: ark-scan
description: Inspect a HarmonyOS Stage-model ArkTS project before modifying it. Use when task scope, file ownership, evidence profile, configuration impact, safe boundaries, or the next Ark command is unclear.
---

# Ark Scan

Map the live project before editing. End with the smallest safe next action.

## Inspect

1. Identify modules, entry abilities, page routing, source and resource layout, test locations, and the feature owner.
2. Trace the current request from UI or entry point through state, service, adapter, repository, and platform boundary before proposing a new manager, event channel, storage key, dependency, or cross-module abstraction.
3. Read only configuration relevant to the request: SDK level, module declaration, permissions, dependencies, build tooling, native/CMake, signing, and lockfiles.
4. Mark protected surfaces: signing, certificates, package identity, SDK compatibility, local device configuration, credentials, production constants, generated output, dependencies, and lockfiles.
5. Assign an evidence profile: `local`, `doc-bound`, `config-bound`, or `runtime-bound`. Retrieve official documentation only when platform facts constrain the change.

## Tool Preflight

When verification or platform evidence may be needed, discover what is available instead of assuming it:

- Official-document lookup or MCP available for API, Kit, permission, and API-level facts.
- Project build/test scripts, DevEco CLI, Hvigor, or IDE-generated command surfaces.
- Device, emulator, hdc, and log access when runtime evidence is in scope.

Record missing tools as constraints, not as failures, unless the user explicitly requested that evidence.

## Deliver: Project Change Map

Report all of the following:

- Affected module and ownership path.
- Entry point and current call path.
- Evidence profile and why it applies.
- Files likely to change and protected surfaces that need approval.
- Official platform constraint, if one affects the request.
- The next command (`$ark-ui`, `$ark-flow`, `$ark-kit`, or `$ark-check`) and the reason.

The scan is complete only when another agent can locate the change boundary without rediscovering it.
