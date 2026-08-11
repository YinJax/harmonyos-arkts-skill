---
name: ark-kit
description: Integrate HarmonyOS ArkTS platform capabilities. Use for permissions, files, Preferences, relational storage, network, WebView, notifications, location, MapKit, GNSS, Bluetooth, media, NAPI/C++ native bridges, device APIs, and system Kit boundaries.
---

# Ark Kit

Treat every system API as a capability boundary.

## Capability First

Inspect the target project's existing imports, module declarations, permissions, SDK level, and adapters before calling a HarmonyOS system API. Prefer the official Kit already used by the project. Treat live project configuration and official documentation as authoritative.

## Permissions

Separate declaration, runtime authorization, and feature behavior:

1. Confirm whether the capability requires a declared permission.
2. Request runtime authorization at the user action or feature entry point when required.
3. Handle grant, denial, cancellation, and unavailable capability separately.
4. Change `module.json5` only after the user explicitly authorizes the permission change.

## Data And I/O

Keep bundled resources, sandbox files, user-visible exports, caches, and durable user data separate. A cache must be recreatable; user data needs an intentional persistence and recovery path. Keep network, I/O, and parsing off the UI-critical path when the platform supports async execution.

## Specialized Work

For MapKit, GNSS, Bluetooth, NAPI/C++, media, or other hardware-facing work, search for an existing manager, adapter, or native bridge first. Preserve the public interface and isolate platform-specific types at that boundary.

## Done

Report the capability, required configuration changes, authorization behavior, failure paths, and runtime verification needed.
