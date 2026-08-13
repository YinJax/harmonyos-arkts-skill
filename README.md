# Ark

<p align="center">
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
  <img alt="HarmonyOS" src="https://img.shields.io/badge/HarmonyOS-Stage%20Model-red.svg">
  <img alt="ArkTS" src="https://img.shields.io/badge/ArkTS-Engineering-2f80ed.svg">
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-111827.svg">
</p>

<p align="center">
  Project-first agent workflow for HarmonyOS Stage-model ArkTS development.
</p>

<p align="center">
  <a href="#zh-cn">中文</a> | <a href="#english">English</a>
</p>

---

<details open>
<summary id="zh-cn"><strong>中文</strong></summary>

## 简介

Ark 是面向 HarmonyOS Stage-model ArkTS 项目的 Codex Skill。它把项目扫描、ArkUI 状态与生命周期、业务异步流、平台 Kit 接入和验证回归组织成一套可复用的 agent 工作流。

Ark 不替代官方文档 MCP，也不替代 DevEco CLI。官方文档 MCP 提供平台事实，DevEco CLI 提供构建和设备证据，Ark 负责把这些事实和证据放进真实项目的安全变更流程里。

## 核心价值

1. **先看项目再改代码**：先识别模块、调用链、状态归属和受保护配置，降低误改项目配置的风险。
2. **把证据分清楚**：用 `local`、`doc-bound`、`config-bound`、`runtime-bound` 区分本地事实、官方约束、配置风险和运行时证据。
3. **让 ArkUI 改动可控**：明确状态归属、生命周期清理和过期异步结果，减少页面状态漂移。
4. **让 Kit 接入可验收**：把 API 约束、权限、配置、失败体验和设备验证收束成能力契约。
5. **让验证能回流修复**：构建、日志或真机失败时，按失败信号回到对应命令继续修。

## 命令

| 命令 | 核心作用 | 开发者收益 |
| --- | --- | --- |
| `use $ark` | 总入口，判断任务该走扫描、UI、业务流、Kit 还是验证。 | 模糊需求快速落到正确路径。 |
| `use $ark-scan` | 扫描项目结构、调用链、受保护配置和安全边界。 | 接手陌生项目时先拿到可改地图。 |
| `use $ark-ui` | 处理 ArkUI 页面、状态、导航和生命周期。 | 减少状态错乱、资源泄漏和旧请求覆盖新 UI。 |
| `use $ark-flow` | 梳理 ViewModel、service、repository、缓存和异步状态。 | 让加载、失败、取消、重试链路清楚可追踪。 |
| `use $ark-kit` | 接入权限、存储、网络、WebView、定位、通知等平台能力。 | 同步处理官方约束、权限配置和设备行为。 |
| `use $ark-check` | 规划或执行构建、打包、安装、日志和设备验证。 | 明确已验证内容、剩余风险和失败归因。 |

## 推荐流程

```text
$ark-scan -> $ark-ui / $ark-flow / $ark-kit -> $ark-check
```

`$ark-scan` 找清楚边界和证据等级；中间命令实现对应契约；`$ark-check` 做最小充分验证，并把失败信号路由回正确位置。

## 安装

```bash
npx skills@latest add YinJax/harmonyos-arkts-skill
```

安装到 Codex 全局范围：

```bash
npx skills@latest add YinJax/harmonyos-arkts-skill -a codex -g
```

更新后请刷新 skill 发现或重启 Codex。当前命令名是 `ark`、`ark-scan`、`ark-ui`、`ark-flow`、`ark-kit`、`ark-check`。

如果你之前安装过旧版本，可能会看到旧命令名：`harmonyos-arkts-skill`、`arkts-scan`、`arkts-ui`、`arkts-flow`、`arkts-capability`、`arkts-verify`。建议更新后统一使用新的短命令。

## 边界

Ark 只沉淀通用鸿蒙工程工作流。产品逻辑、账号、证书、签名配置、本地 SDK 路径、设备参数和生产常量都应留在目标项目中。

## 许可证

MIT

</details>

---

<details>
<summary id="english"><strong>English</strong></summary>

## Overview

Ark is a Codex Skill for HarmonyOS Stage-model ArkTS projects. It turns project scanning, ArkUI state and lifecycle work, async business flows, platform Kit integration, and verification into a reusable agent workflow.

Ark does not replace the official documentation MCP or DevEco CLI. The official documentation MCP provides platform facts, DevEco CLI provides build and device evidence, and Ark places both into a safe project-change process.

## Core Value

1. **Inspect before editing**: Identify modules, call paths, state ownership, and protected configuration before changing code.
2. **Separate evidence levels**: Use `local`, `doc-bound`, `config-bound`, and `runtime-bound` to separate local facts, official constraints, config risk, and runtime evidence.
3. **Control ArkUI changes**: Make state ownership, lifecycle cleanup, and stale async results explicit.
4. **Make Kit work verifiable**: Turn API constraints, permissions, config, failure behavior, and device checks into a capability contract.
5. **Route failures back**: Send build, log, or device failures back to the command that owns the broken contract.

## Commands

| Command | Core role | Developer benefit |
| --- | --- | --- |
| `use $ark` | Route work to scan, UI, flow, Kit, or verification. | Turn broad requests into the right path. |
| `use $ark-scan` | Inspect structure, call paths, protected config, and edit boundaries. | Map unfamiliar projects before editing. |
| `use $ark-ui` | Handle ArkUI pages, state, navigation, and lifecycle. | Reduce state drift, leaks, and stale UI updates. |
| `use $ark-flow` | Shape ViewModel, service, repository, cache, and async states. | Keep loading, failure, cancel, and retry paths traceable. |
| `use $ark-kit` | Integrate permissions, storage, networking, WebView, location, notifications, and platform APIs. | Align official constraints, permissions, config, and device behavior. |
| `use $ark-check` | Plan or run build, package, install, log, and device verification. | Show verified evidence, remaining risk, and failure ownership. |

## Recommended Route

```text
$ark-scan -> $ark-ui / $ark-flow / $ark-kit -> $ark-check
```

`$ark-scan` establishes boundaries and evidence level. The middle commands implement the relevant contract. `$ark-check` performs the smallest sufficient verification and routes failures back to the right owner.

## Installation

```bash
npx skills@latest add YinJax/harmonyos-arkts-skill
```

Install globally for Codex:

```bash
npx skills@latest add YinJax/harmonyos-arkts-skill -a codex -g
```

After updating, refresh skill discovery or restart Codex. The current command names are `ark`, `ark-scan`, `ark-ui`, `ark-flow`, `ark-kit`, and `ark-check`.

Older installs may still show the previous names: `harmonyos-arkts-skill`, `arkts-scan`, `arkts-ui`, `arkts-flow`, `arkts-capability`, and `arkts-verify`. Prefer the new shorter names after updating.

## Scope

Ark stores reusable HarmonyOS engineering workflow rules only. Product logic, credentials, certificates, signing configuration, local SDK paths, device parameters, and production constants remain in the target project.

## License

MIT

</details>
