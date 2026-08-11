# HarmonyOS ArkTS Engineering

A reusable Codex skill for implementing and modifying HarmonyOS Stage-model ArkTS projects.

It guides project recognition, ArkUI state and lifecycle work, application layering, system capabilities, and risk-proportionate verification. It intentionally excludes product-specific business rules and local signing or SDK configuration.

## Install

Copy this directory into your Codex skills directory, typically `~/.codex/skills/harmonyos-arkts-engineering`, then restart or refresh Codex skill discovery.

## Use

Ask Codex to use `$harmonyos-arkts-engineering` for ArkUI pages, ArkTS business flows, permissions, persistence, files, networking, native bridges, tests, builds, or device verification.

## Structure

- `SKILL.md`: Core workflow and triggering description.
- `references/`: Architecture, platform-capability, and verification guidance.
- `agents/openai.yaml`: Codex UI metadata.

## Scope

The skill is designed for reusable HarmonyOS engineering practices. It does not include proprietary product logic, credentials, certificates, local paths, or device-specific constants.

## License

MIT
