---
name: ark-flow
description: Implement HarmonyOS ArkTS layered business and async flows. Use for ViewModel, service, repository, DTO, cache, parser, loading, error handling, navigation coordination, request identity, stale completion, and UI-to-data-source orchestration.
---

# ArkTS Flow

Make the user-visible operation legible from component to data source.

## Boundaries

Keep components focused on rendering and direct interaction. Put coordination and state transitions in the existing ViewModel or manager. Put storage, parsing, network, and platform I/O behind services, adapters, or repositories. Follow the local pattern when one exists.

## Async Path

For work visible to the user:

1. Start from one owner and set pending state.
2. Call the existing service, adapter, or repository.
3. Apply success only if the request is still current.
4. Surface failure through the project's existing message or error state.
5. Clear pending on every terminal outcome.

## Data Contracts

Use existing DTO, domain model, cache key, and repository conventions. Validate external input before parsing. Do not duplicate mutable copies of the same user-visible fact across component, ViewModel, and service layers.

## Done

Report the call path, state transitions, success/failure behavior, stale-result handling, and tests or verification still needed.
