# Ark

面向 HarmonyOS Stage-model ArkTS 项目的 Codex Skill：把项目扫描、ArkUI 状态与生命周期、业务异步流、平台 Kit 接入和验证回归组织成一套可复用的 agent 工作流。

Ark 不替代官方文档 MCP，也不替代 DevEco CLI。官方文档 MCP 提供平台事实，DevEco CLI 提供构建和设备证据，Ark 负责把这些事实和证据放进真实项目的安全变更流程里。

## 中文说明

### 核心价值

1. **项目先行**：修改前先识别模块、页面、调用链、状态归属和受保护配置，避免把项目级问题当成单文件改动。
2. **证据分级**：用 `local`、`doc-bound`、`config-bound`、`runtime-bound` 标记任务需要的证据，让 agent 知道什么时候查官方文档、什么时候跑 DevEco 命令、什么时候先要用户授权。
3. **ArkUI 工程化**：修改页面时交付 State/Lifecycle Ledger，说明状态由谁拥有、在哪里初始化、在哪里清理、如何处理过期异步结果。
4. **平台能力契约化**：接入系统 Kit 时交付 Capability Contract，把官方 API 约束、权限声明、运行时授权、配置变更、失败体验和验收方式放在同一个判断框架里。
5. **验证可追踪**：验证失败时按失败信号分流回 `$ark-ui`、`$ark-flow`、`$ark-kit` 或 `$ark-scan`，避免无依据地继续改代码。

### 命令

| 命令 | 功能 | 帮助开发者 |
| --- | --- | --- |
| `use $ark` | 总入口和任务路由。判断需求属于扫描、UI、业务流、平台能力还是验证。 | 把模糊需求变成明确执行路径，减少选错 skill 或直接乱改的风险。 |
| `use $ark-scan` | 项目扫描。识别 Stage 模型结构、模块归属、调用链、配置风险和可修改边界。 | 接手陌生项目时快速建立地图，知道哪里能改、哪里需要谨慎。 |
| `use $ark-ui` | ArkUI 页面、组件、状态、导航和生命周期处理。 | 减少状态错乱、重复刷新、资源未释放、旧异步结果覆盖新 UI 等问题。 |
| `use $ark-flow` | ViewModel、service、repository、DTO、缓存、加载和错误状态等异步业务流。 | 把 UI、业务协调、数据源和错误处理拆清楚，让请求、重试、取消和失败状态可追踪。 |
| `use $ark-kit` | 权限、文件、Preferences、数据库、网络、WebView、定位、通知、媒体、设备 API 等平台能力。 | 接入 HarmonyOS Kit 时同步处理 API 约束、权限、配置、兼容性和真实设备行为。 |
| `use $ark-check` | 验证计划和结果归因。发现构建、打包、安装、日志、设备验证命令并记录结果。 | 明确哪些已经验证、哪些只是推断，失败后能回到正确命令继续修。 |

### 推荐流程

```text
$ark-scan -> $ark-ui / $ark-flow / $ark-kit -> $ark-check
```

`$ark-scan` 负责找清楚项目边界和证据等级；`$ark-ui`、`$ark-flow`、`$ark-kit` 负责实现对应契约；`$ark-check` 负责按风险选择最小充分验证，并把失败信号路由回正确位置。

### 安装

```bash
npx skills@latest add YinJax/harmonyos-arkts-skill
```

安装到 Codex 全局范围：

```bash
npx skills@latest add YinJax/harmonyos-arkts-skill -a codex -g
```

更新后请刷新 skill 发现或重启 Codex。当前命令名是 `ark`、`ark-scan`、`ark-ui`、`ark-flow`、`ark-kit`、`ark-check`。

如果你之前安装过旧版本，可能会看到旧命令名：`harmonyos-arkts-skill`、`arkts-scan`、`arkts-ui`、`arkts-flow`、`arkts-capability`、`arkts-verify`。建议更新后统一使用新的短命令。

## English

Ark is a Codex Skill for HarmonyOS Stage-model ArkTS projects. It turns project inspection, ArkUI state and lifecycle work, async business flows, platform Kit integration, and verification into a reusable agent workflow.

Ark does not replace the official documentation MCP or DevEco CLI. The official documentation MCP provides platform facts, DevEco CLI provides build and device evidence, and Ark places both into a safe project-change process.

### Value

1. **Project-first changes**: Inspect modules, pages, call paths, state ownership, and protected configuration before editing.
2. **Evidence profiles**: Classify work as `local`, `doc-bound`, `config-bound`, or `runtime-bound` so the agent knows when to inspect the project, consult official docs, discover DevEco commands, or request approval.
3. **ArkUI engineering discipline**: Produce a State/Lifecycle Ledger for page changes so state ownership, initialization, cleanup, and stale async completions are explicit.
4. **Capability contracts**: Produce a Capability Contract for system Kit work, covering official API constraints, permissions, runtime authorization, config changes, failure behavior, and acceptance checks.
5. **Traceable verification**: Route failures back to `$ark-ui`, `$ark-flow`, `$ark-kit`, or `$ark-scan` based on the observed evidence instead of continuing to edit blindly.

### Commands

| Command | What it does | How it helps developers |
| --- | --- | --- |
| `use $ark` | Router and control entry point. Chooses scanning, UI, flow, Kit, or verification. | Turns broad requests into a concrete path and reduces accidental unsafe edits. |
| `use $ark-scan` | Inspects Stage-model structure, ownership, call paths, protected config, and safe edit boundaries. | Helps developers map unfamiliar projects before changing code. |
| `use $ark-ui` | Handles ArkUI pages, components, state, navigation, and lifecycle. | Reduces state drift, repeated rendering, leaked listeners/timers, and stale async UI updates. |
| `use $ark-flow` | Handles ViewModel, service, repository, DTO, cache, loading, cancellation, and error flows. | Keeps UI, business coordination, data sources, and failure handling traceable. |
| `use $ark-kit` | Handles permissions, files, Preferences, databases, networking, WebView, location, notifications, media, and device APIs. | Keeps HarmonyOS Kit work aligned with API constraints, permissions, configuration, compatibility, and runtime behavior. |
| `use $ark-check` | Plans or runs verification through build, package, install, device, log, and review evidence. | Makes verified results, unverified risks, and failure ownership explicit. |

### Recommended Route

```text
$ark-scan -> $ark-ui / $ark-flow / $ark-kit -> $ark-check
```

`$ark-scan` establishes boundaries and evidence level. `$ark-ui`, `$ark-flow`, and `$ark-kit` implement the relevant contract. `$ark-check` chooses the smallest sufficient verification path and routes failures back to the right command.

### Installation

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

Ark stores reusable workflow rules only. Product logic, credentials, certificates, signing configuration, local SDK paths, device parameters, and production constants remain in the target project.

## License

MIT
