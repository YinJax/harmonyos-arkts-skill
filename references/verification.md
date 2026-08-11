# Verification

## Choose The Smallest Sufficient Evidence

| Change risk | Minimum evidence |
| --- | --- |
| Local ArkTS or resource change | Focused static inspection and the closest existing test when available |
| Shared state, service, parser, or persistence change | Relevant unit or integration tests, including an error path |
| Permission, native bridge, dependency, or build configuration change | Relevant tests plus an explicit build request or authorized build verification |
| Device capability, rendering, location, or external service behavior | Authorized runtime or device verification with observable acceptance checks |

## Test Behavior At Seams

Test the public behavior of a component, ViewModel, service, or adapter rather than private implementation details. Cover the intended outcome, a meaningful failure, and an edge condition created by the changed contract. Reuse the project's test runner and directory conventions.

## Build And Device Work

Do not launch DevEco Studio, emulators, device installation, or a full Hvigor build unless the user asks to compile, package, install, test on a device, or otherwise verify runtime behavior. When verification is run, report the exact command or check and its result. When it is skipped, state that the remaining risk is unverified runtime behavior.

## Completion

Before reporting completion, re-read the requested outcome and confirm that every changed surface has corresponding evidence or an explicit unverified boundary. Keep the final report limited to the user-visible result, changed files, verification evidence, and material risks.
