# Ark

<p align="center">
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
  <img alt="HarmonyOS" src="https://img.shields.io/badge/HarmonyOS-Stage%20Model-red.svg">
  <img alt="ArkTS" src="https://img.shields.io/badge/ArkTS-Workflow-2f80ed.svg">
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-111827.svg">
</p>

<p align="center">
  <strong>Project-first agent workflow for HarmonyOS ArkTS development.</strong>
</p>

<p align="center">
  <a href="#zh-cn">中文</a> · <a href="#english">English</a>
</p>

---

<details open>
<summary id="zh-cn"><strong>中文</strong></summary>

## 一句话

Ark 是一个面向 HarmonyOS Stage-model ArkTS 项目的 Codex Skill。它不复述官方 API，也不替代 DevEco CLI，而是把“项目事实、官方约束、构建/设备证据”组织成一套可执行的安全变更流程。

## 适合用在

- 接手陌生 HarmonyOS ArkTS 项目，先识别模块、调用链和安全边界。
- 修改 ArkUI 页面、状态、导航、生命周期和异步 UI 更新。
- 梳理 ViewModel、service、repository、缓存、加载、失败和重试链路。
- 接入权限、存储、网络、WebView、定位、通知等 HarmonyOS Kit 能力。
- 为构建、安装、日志、真机验证和失败归因建立最小充分验证路线。

## 核心价值

| 价值 | 说明 |
| --- | --- |
| Project-first | 先看项目结构和变更边界，再决定怎么改。 |
| Evidence-aware | 区分本地事实、官方文档约束、配置风险和运行时证据。 |
| Contract-driven | UI、业务流、平台能力都以明确契约交付。 |
| Verification-led | 每次非平凡改动都能说明验证过什么、还剩什么风险。 |

## 命令矩阵

| 命令 | 核心作用 | 开发者收益 |
| --- | --- | --- |
| `ark` | 总入口，选择扫描、UI、业务流、Kit 或验证路径。 | 模糊需求快速落到正确执行面。 |
| `ark-scan` | 扫描结构、调用链、受保护配置和改动边界。 | 接手项目先拿到可改地图。 |
| `ark-ui` | 处理 ArkUI 状态、导航、生命周期和渲染副作用。 | 减少状态漂移、泄漏和旧请求覆盖。 |
| `ark-flow` | 梳理 ViewModel、service、repository 和异步状态。 | 让加载、失败、取消、重试可追踪。 |
| `ark-kit` | 接入权限、存储、网络、WebView、定位、通知等能力。 | 同步处理官方约束、权限配置和设备行为。 |
| `ark-check` | 规划或执行构建、打包、安装、日志和设备验证。 | 明确验证证据、剩余风险和失败归因。 |

## 推荐流程

```text
ark-scan -> ark-ui / ark-flow / ark-kit -> ark-check
```

`ark-scan` 先确认项目边界和证据等级；`ark-ui`、`ark-flow`、`ark-kit` 分别交付 UI、业务流、平台能力契约；`ark-check` 做最小充分验证，并把失败信号路由回正确命令。

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

## One-liner

Ark is a Codex Skill for HarmonyOS Stage-model ArkTS projects. It does not copy official API docs or replace DevEco CLI; it turns project facts, official constraints, and build/device evidence into a safe change workflow.

## Best for

- Mapping an unfamiliar HarmonyOS ArkTS project before editing.
- Changing ArkUI pages, state, navigation, lifecycle, and async UI updates.
- Shaping ViewModel, service, repository, cache, loading, failure, and retry flows.
- Integrating HarmonyOS Kit capabilities such as permissions, storage, networking, WebView, location, and notifications.
- Planning the smallest sufficient build, install, log, device, and failure-triage verification path.

## Core Value

| Value | Meaning |
| --- | --- |
| Project-first | Inspect structure and edit boundaries before changing code. |
| Evidence-aware | Separate local facts, official constraints, config risk, and runtime evidence. |
| Contract-driven | Deliver UI, async flow, and platform capability work as explicit contracts. |
| Verification-led | State what was verified, what remains risky, and who owns failures. |

## Command Matrix

| Command | Core role | Developer benefit |
| --- | --- | --- |
| `ark` | Route work to scan, UI, flow, Kit, or verification. | Turn broad requests into the right execution path. |
| `ark-scan` | Inspect structure, call paths, protected config, and edit boundaries. | Map safe changes before editing. |
| `ark-ui` | Handle ArkUI state, navigation, lifecycle, and render side effects. | Reduce state drift, leaks, and stale updates. |
| `ark-flow` | Shape ViewModel, service, repository, and async states. | Keep loading, failure, cancel, and retry paths traceable. |
| `ark-kit` | Integrate permissions, storage, networking, WebView, location, notifications, and platform APIs. | Align official constraints, permissions, config, and device behavior. |
| `ark-check` | Plan or run build, package, install, log, and device verification. | Show evidence, remaining risk, and failure ownership. |

## Recommended Route

```text
ark-scan -> ark-ui / ark-flow / ark-kit -> ark-check
```

`ark-scan` establishes project boundaries and evidence level. `ark-ui`, `ark-flow`, and `ark-kit` implement the relevant contract. `ark-check` performs the smallest sufficient verification and routes failures back to the right command.

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
