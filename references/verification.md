# Verification

Use this reference when a change touches more than one surface or when the required evidence is unclear.

## Evidence Selection

| Evidence profile | Changed surface | Minimum evidence | Escalate when |
| --- | --- | --- | --- |
| `local` | Local ArkTS, ArkUI, or resource change inside known boundaries. | Focused inspection and closest existing test/check. | Rendering, navigation, lifecycle, or user-visible behavior changes. |
| `doc-bound` | Platform API behavior, permission semantics, API level, or compatibility. | Official-document constraint plus local inspection/test. | The documented behavior changes config, error handling, or runtime availability. |
| `config-bound` | Permission declaration, dependency, SDK, module config, native bridge, package identity, signing, or lockfile. | Explicit approval plus relevant test and authorized build. | The config change affects packaging, signing, installation, or native output. |
| `runtime-bound` | Device capability, rendering, location, external service, install, logs, or hardware-dependent behavior. | Authorized runtime/device check with acceptance criteria. | Static tests or simulator checks cannot observe the intended outcome. |

## Verification Manifest

Use this table in the final report. Discover commands from the target project and available CLI help; treat copied commands as stale until rediscovered.

| Changed surface | Evidence profile | Acceptance criterion | Project command/check | Authorization | Result / remaining risk |
| --- | --- | --- | --- | --- | --- |

Test behavior at the public boundary of a component, ViewModel, service, repository, or adapter. Cover intended outcome, meaningful failure, and one edge condition created by the changed contract.

Build, package, install, emulator, device, and log work require the user's requested verification scope. If skipped, name the remaining runtime risk rather than implying a full pass.
