# HarmonyOS ArkTS Engineering

<p align="center">
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
  <img alt="HarmonyOS" src="https://img.shields.io/badge/HarmonyOS-Stage%20Model-red.svg">
  <img alt="ArkTS" src="https://img.shields.io/badge/ArkTS-Engineering-2f80ed.svg">
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-111827.svg">
</p>

<p align="center">
  A reusable Codex skill for building, modifying, reviewing, and verifying HarmonyOS Stage-model ArkTS projects.
</p>

<p align="center">
  <a href="#中文">中文</a> | <a href="#english">English</a>
</p>

---

<details open>
<summary id="中文"><strong>中文</strong></summary>

## 简介

`harmonyos-arkts-engineering` 是一个面向 HarmonyOS / 鸿蒙 Stage 模型 ArkTS 项目的通用 Codex Skill。它把项目识别、安全边界、ArkUI 状态与生命周期、分层业务实现、系统能力接入、数据处理和验证路线整理成可复用的工程工作流。

这个 Skill 不包含任何具体业务规则。它适合被用于新的鸿蒙项目、已有 ArkTS 工程维护、页面与组件开发、服务层改造、权限与系统能力接入、构建验证和代码审查。

## 适用场景

- 实现或修改 ArkUI 页面、组件、状态管理和生命周期逻辑。
- 梳理 `ViewModel`、`service`、`repository`、DTO、缓存、网络和异步流程。
- 接入权限、文件、偏好存储、关系型存储、网络、定位、通知、WebView、原生桥接等系统能力。
- 为 HarmonyOS 项目制定静态检查、构建、单元测试、设备验证和回归检查路线。
- 在改动前识别项目边界，避免修改签名、证书、SDK、本地设备配置和业务私有常量。

## 为什么使用

| 能力 | 作用 |
| --- | --- |
| 工程识别与安全边界 | 先确认项目结构、模块职责和不可触碰区域，降低误改环境配置的风险。 |
| ArkUI 状态与生命周期 | 让页面状态、渲染、副作用和资源释放更可预测。 |
| 分层与异步业务实现 | 把页面、状态、服务、数据源和错误处理分开，减少 UI 与业务耦合。 |
| 系统能力与数据处理 | 为权限、文件、网络、存储和设备能力提供统一检查路径。 |
| 质量与验证路线 | 根据改动风险选择静态检查、构建、测试、日志和真机验证。 |

## 安装

把本仓库复制到 Codex Skills 目录：

```bash
~/.codex/skills/harmonyos-arkts-engineering
```

然后重启 Codex，或刷新 Skill 发现。

也可以从 GitHub 安装：

```bash
git clone https://github.com/Yjx98/harmonyos-arkts-engineering.git ~/.codex/skills/harmonyos-arkts-engineering
```

## 使用示例

```text
use $harmonyos-arkts-engineering 帮我实现一个 ArkUI 页面，并保持现有项目分层风格。
```

```text
use $harmonyos-arkts-engineering 检查这次 HarmonyOS ArkTS 改动需要怎么验证。
```

```text
use $harmonyos-arkts-engineering 帮我接入权限、数据持久化和异步错误处理。
```

## 仓库结构

```text
harmonyos-arkts-engineering/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── arkui-and-architecture.md
│   ├── platform-capabilities.md
│   └── verification.md
├── LICENSE
└── README.md
```

## 边界

本 Skill 只沉淀通用鸿蒙工程能力，不包含专有业务逻辑、账号、证书、签名配置、SDK 本地路径、设备私有参数或生产环境常量。

## 许可证

MIT

</details>

---

<details>
<summary id="english"><strong>English</strong></summary>

## Overview

`harmonyos-arkts-engineering` is a reusable Codex skill for HarmonyOS Stage-model ArkTS projects. It packages practical workflows for project recognition, safe editing boundaries, ArkUI state and lifecycle behavior, layered business implementation, platform capabilities, data handling, and risk-based verification.

The skill is intentionally business-neutral. Use it for new HarmonyOS apps, existing ArkTS project maintenance, ArkUI pages and components, service-layer changes, permissions and system APIs, build verification, and code review.

## Use Cases

- Build or modify ArkUI pages, components, state models, and lifecycle behavior.
- Organize `ViewModel`, `service`, `repository`, DTO, cache, networking, and async flows.
- Work with permissions, files, preferences, relational storage, networking, location, notifications, WebView, or native bridges.
- Plan static checks, builds, unit tests, device validation, logs, and regression coverage.
- Detect protected project areas before editing signing, certificates, SDK settings, local device config, or private constants.

## Why This Skill

| Area | What it helps with |
| --- | --- |
| Project recognition and safety boundaries | Identify project shape, module ownership, and protected files before changing code. |
| ArkUI state and lifecycle | Keep UI state, rendering, side effects, and cleanup predictable. |
| Layering and async business flows | Separate UI, state, services, data sources, and error handling. |
| Platform capabilities and data handling | Provide a consistent checklist for permissions, files, networking, storage, and device APIs. |
| Quality and verification | Match validation effort to the risk and scope of each change. |

## Installation

Copy this repository into your Codex skills directory:

```bash
~/.codex/skills/harmonyos-arkts-engineering
```

Then restart Codex or refresh skill discovery.

You can also install from GitHub:

```bash
git clone https://github.com/Yjx98/harmonyos-arkts-engineering.git ~/.codex/skills/harmonyos-arkts-engineering
```

## Example Prompts

```text
use $harmonyos-arkts-engineering to implement an ArkUI page while preserving the existing project layering style.
```

```text
use $harmonyos-arkts-engineering to decide how this HarmonyOS ArkTS change should be verified.
```

```text
use $harmonyos-arkts-engineering to add permission handling, persistence, and async error handling.
```

## Repository Layout

```text
harmonyos-arkts-engineering/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── arkui-and-architecture.md
│   ├── platform-capabilities.md
│   └── verification.md
├── LICENSE
└── README.md
```

## Scope

This skill captures reusable HarmonyOS engineering practice only. It does not include proprietary product logic, accounts, credentials, certificates, signing config, local SDK paths, private device parameters, or production constants.

## License

MIT

</details>
