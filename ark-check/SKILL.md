---
name: ark-check
description: Plan or run verification for HarmonyOS ArkTS changes. Use when the user asks how to test, review, build, compile, package, install, run on device, inspect logs, validate permissions, or decide the minimum evidence for a HarmonyOS change.
---

# Ark Check

Choose the smallest sufficient evidence for the changed surface.

## Evidence Ladder

| Change risk | Minimum evidence |
| --- | --- |
| Local ArkTS or resource change | Focused static inspection and closest existing test when available |
| Shared state, service, parser, or persistence change | Relevant unit or integration tests, including an error path |
| Permission, native bridge, dependency, or build configuration change | Relevant tests plus explicit build request or authorized build verification |
| Device capability, rendering, location, or external service behavior | Authorized runtime or device verification with observable acceptance checks |

## Test At Seams

Test public behavior of a component, ViewModel, service, repository, or adapter rather than private implementation details. Cover intended outcome, meaningful failure, and an edge condition created by the changed contract.

## Build And Device Boundary

Do not launch DevEco Studio, emulators, device installation, full Hvigor builds, or device log streams unless the user asks to compile, package, install, test on device, or verify runtime behavior. When verification runs, report the exact command or check and result.

## Done

Before reporting completion, confirm every changed surface has corresponding evidence or an explicit unverified boundary. Keep the report to user-visible result, changed files, verification evidence, and material risks.
