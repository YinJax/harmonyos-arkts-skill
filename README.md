# ArkTS Project Skill

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
  <a href="#zh-cn">&#20013;&#25991;</a> | <a href="#english">English</a>
</p>

---

<details open>
<summary id="zh-cn"><strong>&#20013;&#25991;</strong></summary>

## &#31616;&#20171;

`arkts-project-skill` &#26159;&#19968;&#20010;&#38754;&#21521; HarmonyOS / &#40511;&#33945; Stage &#27169;&#22411; ArkTS &#39033;&#30446;&#30340;&#36890;&#29992; Codex Skill&#12290;&#23427;&#25226;&#39033;&#30446;&#35782;&#21035;&#12289;&#23433;&#20840;&#36793;&#30028;&#12289;ArkUI &#29366;&#24577;&#19982;&#29983;&#21629;&#21608;&#26399;&#12289;&#20998;&#23618;&#19994;&#21153;&#23454;&#29616;&#12289;&#31995;&#32479;&#33021;&#21147;&#25509;&#20837;&#12289;&#25968;&#25454;&#22788;&#29702;&#21644;&#39564;&#35777;&#36335;&#32447;&#25972;&#29702;&#25104;&#21487;&#22797;&#29992;&#30340;&#24037;&#31243;&#24037;&#20316;&#27969;&#12290;

&#36825;&#20010; Skill &#19981;&#21253;&#21547;&#20219;&#20309;&#20855;&#20307;&#19994;&#21153;&#35268;&#21017;&#12290;&#23427;&#36866;&#21512;&#29992;&#20110;&#26032;&#30340;&#40511;&#33945;&#39033;&#30446;&#12289;&#24050;&#26377; ArkTS &#24037;&#31243;&#32500;&#25252;&#12289;&#39029;&#38754;&#19982;&#32452;&#20214;&#24320;&#21457;&#12289;&#26381;&#21153;&#23618;&#25913;&#36896;&#12289;&#26435;&#38480;&#19982;&#31995;&#32479;&#33021;&#21147;&#25509;&#20837;&#12289;&#26500;&#24314;&#39564;&#35777;&#21644;&#20195;&#30721;&#23457;&#26597;&#12290;

## &#36866;&#29992;&#22330;&#26223;

- &#23454;&#29616;&#25110;&#20462;&#25913; ArkUI &#39029;&#38754;&#12289;&#32452;&#20214;&#12289;&#29366;&#24577;&#31649;&#29702;&#21644;&#29983;&#21629;&#21608;&#26399;&#36923;&#36753;&#12290;
- &#26803;&#29702; `ViewModel`&#12289;`service`&#12289;`repository`&#12289;DTO&#12289;&#32531;&#23384;&#12289;&#32593;&#32476;&#21644;&#24322;&#27493;&#27969;&#31243;&#12290;
- &#25509;&#20837;&#26435;&#38480;&#12289;&#25991;&#20214;&#12289;&#20559;&#22909;&#23384;&#20648;&#12289;&#20851;&#31995;&#22411;&#23384;&#20648;&#12289;&#32593;&#32476;&#12289;&#23450;&#20301;&#12289;&#36890;&#30693;&#12289;WebView&#12289;&#21407;&#29983;&#26725;&#25509;&#31561;&#31995;&#32479;&#33021;&#21147;&#12290;
- &#20026; HarmonyOS &#39033;&#30446;&#21046;&#23450;&#38745;&#24577;&#26816;&#26597;&#12289;&#26500;&#24314;&#12289;&#21333;&#20803;&#27979;&#35797;&#12289;&#35774;&#22791;&#39564;&#35777;&#21644;&#22238;&#24402;&#26816;&#26597;&#36335;&#32447;&#12290;
- &#22312;&#25913;&#21160;&#21069;&#35782;&#21035;&#39033;&#30446;&#36793;&#30028;&#65292;&#36991;&#20813;&#20462;&#25913;&#31614;&#21517;&#12289;&#35777;&#20070;&#12289;SDK&#12289;&#26412;&#22320;&#35774;&#22791;&#37197;&#32622;&#21644;&#19994;&#21153;&#31169;&#26377;&#24120;&#37327;&#12290;

## &#20026;&#20160;&#20040;&#20351;&#29992;

| &#33021;&#21147; | &#20316;&#29992; |
| --- | --- |
| &#24037;&#31243;&#35782;&#21035;&#19982;&#23433;&#20840;&#36793;&#30028; | &#20808;&#30830;&#35748;&#39033;&#30446;&#32467;&#26500;&#12289;&#27169;&#22359;&#32844;&#36131;&#21644;&#19981;&#21487;&#35302;&#30896;&#21306;&#22495;&#65292;&#38477;&#20302;&#35823;&#25913;&#29615;&#22659;&#37197;&#32622;&#30340;&#39118;&#38505;&#12290; |
| ArkUI &#29366;&#24577;&#19982;&#29983;&#21629;&#21608;&#26399; | &#35753;&#39029;&#38754;&#29366;&#24577;&#12289;&#28210;&#26579;&#12289;&#21103;&#20316;&#29992;&#21644;&#36164;&#28304;&#37322;&#25918;&#26356;&#21487;&#39044;&#27979;&#12290; |
| &#20998;&#23618;&#19982;&#24322;&#27493;&#19994;&#21153;&#23454;&#29616; | &#25226;&#39029;&#38754;&#12289;&#29366;&#24577;&#12289;&#26381;&#21153;&#12289;&#25968;&#25454;&#28304;&#21644;&#38169;&#35823;&#22788;&#29702;&#20998;&#24320;&#65292;&#20943;&#23569; UI &#19982;&#19994;&#21153;&#32806;&#21512;&#12290; |
| &#31995;&#32479;&#33021;&#21147;&#19982;&#25968;&#25454;&#22788;&#29702; | &#20026;&#26435;&#38480;&#12289;&#25991;&#20214;&#12289;&#32593;&#32476;&#12289;&#23384;&#20648;&#21644;&#35774;&#22791;&#33021;&#21147;&#25552;&#20379;&#32479;&#19968;&#26816;&#26597;&#36335;&#24452;&#12290; |
| &#36136;&#37327;&#19982;&#39564;&#35777;&#36335;&#32447; | &#26681;&#25454;&#25913;&#21160;&#39118;&#38505;&#36873;&#25321;&#38745;&#24577;&#26816;&#26597;&#12289;&#26500;&#24314;&#12289;&#27979;&#35797;&#12289;&#26085;&#24535;&#21644;&#30495;&#26426;&#39564;&#35777;&#12290; |

## &#23433;&#35013;

&#25512;&#33616;&#20351;&#29992; `skills` &#23433;&#35013;&#22120;&#12290;&#22914;&#26524;&#21478;&#22806;&#20351;&#29992; Git &#22797;&#21046;&#25110;&#25163;&#21160;&#23433;&#35013;&#65292;&#35831;&#19981;&#35201;&#21516;&#26102;&#25226;&#21516;&#19968; Skill &#23433;&#35013;&#21040;&#21516;&#19968;&#20301;&#32622;&#12290;&#38656;&#35201;&#26412;&#26426;&#24050;&#23433;&#35013; Node.js 18+&#65288;&#21253;&#21547; `npx`&#65289;&#12290;

### &#24555;&#36895;&#23433;&#35013;&#65288;&#25512;&#33616;&#65289;

```bash
npx skills@latest add Yjx98/arkts-project-skill
```

### &#25351;&#23450;&#23433;&#35013;&#65306;Codex &#20840;&#23616;&#33539;&#22260;

```bash
npx skills@latest add Yjx98/arkts-project-skill -a codex -g
```

`-a codex` &#21482;&#21521; Codex &#23433;&#35013;&#65307;`-g` &#35753;&#23427;&#22312;&#25152;&#26377;&#39033;&#30446;&#20013;&#21487;&#29992;&#12290;&#19981;&#24102;&#21442;&#25968;&#30340;&#24555;&#36895;&#23433;&#35013;&#20250;&#30001; `skills` CLI &#24341;&#23548;&#36873;&#25321;&#23433;&#35013;&#33539;&#22260;&#12290;

### &#26356;&#26032;

```bash
npx skills@latest update arkts-project-skill -g
```

`npx` &#20250;&#22312;&#38656;&#35201;&#26102;&#19979;&#36733;&#24182;&#36816;&#34892;&#26368;&#26032;&#29256;&#26412;&#30340; `skills` CLI&#65292;&#26080;&#38656;&#20808;&#20840;&#23616;&#23433;&#35013; npm &#21253;&#12290;&#23433;&#35013;&#21518;&#37325;&#21551; Codex&#65292;&#25110;&#21047;&#26032; Skill &#21457;&#29616;&#12290;

### &#22791;&#36873;&#65306;Git &#23433;&#35013;

&#22914;&#26524;&#20320;&#19981;&#20351;&#29992; Node.js / npm&#65292;&#35831;&#30830;&#35748;&#26412;&#26426;&#24050;&#23433;&#35013; `git`&#65292;&#24182;&#22312;&#32456;&#31471;&#20013;&#21487;&#20197;&#36816;&#34892; `git --version`&#12290;

### macOS / Linux

```bash
mkdir -p ~/.codex/skills
git clone --depth 1 https://github.com/Yjx98/arkts-project-skill.git ~/.codex/skills/arkts-project-skill
```

&#26356;&#26032;&#21040;&#26368;&#26032;&#29256;&#26412;&#65306;

```bash
git -C ~/.codex/skills/arkts-project-skill pull --ff-only
```

### Windows PowerShell

```powershell
$skills = Join-Path $env:USERPROFILE ".codex\skills"
New-Item -ItemType Directory -Force -Path $skills
git clone --depth 1 https://github.com/Yjx98/arkts-project-skill.git (Join-Path $skills "arkts-project-skill")
```

&#26356;&#26032;&#21040;&#26368;&#26032;&#29256;&#26412;&#65306;

```powershell
git -C "$env:USERPROFILE\.codex\skills\arkts-project-skill" pull --ff-only
```

### &#25163;&#21160;&#23433;&#35013;

&#19979;&#36733;&#26412;&#20179;&#24211;&#21518;&#65292;&#25226;&#25972;&#20010; `arkts-project-skill` &#25991;&#20214;&#22841;&#22797;&#21046;&#21040;&#65306;

```text
~/.codex/skills/arkts-project-skill
```

Windows &#23545;&#24212;&#36335;&#24452;&#36890;&#24120;&#26159;&#65306;

```text
%USERPROFILE%\.codex\skills\arkts-project-skill
```

## &#20351;&#29992;&#31034;&#20363;

- &#20351;&#29992; `use $arkts-project-skill` &#23454;&#29616; ArkUI &#39029;&#38754;&#65292;&#24182;&#20445;&#25345;&#29616;&#26377;&#39033;&#30446;&#20998;&#23618;&#39118;&#26684;&#12290;
- &#20351;&#29992; `use $arkts-project-skill` &#26816;&#26597; HarmonyOS ArkTS &#25913;&#21160;&#38656;&#35201;&#24590;&#20040;&#39564;&#35777;&#12290;
- &#20351;&#29992; `use $arkts-project-skill` &#25509;&#20837;&#26435;&#38480;&#12289;&#25968;&#25454;&#25345;&#20037;&#21270;&#21644;&#24322;&#27493;&#38169;&#35823;&#22788;&#29702;&#12290;

## &#20179;&#24211;&#32467;&#26500;

```text
arkts-project-skill/
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- arkui-and-architecture.md
|   |-- platform-capabilities.md
|   `-- verification.md
|-- LICENSE
`-- README.md
```

## &#36793;&#30028;

&#26412; Skill &#21482;&#27785;&#28096;&#36890;&#29992;&#40511;&#33945;&#24037;&#31243;&#33021;&#21147;&#65292;&#19981;&#21253;&#21547;&#19987;&#26377;&#19994;&#21153;&#36923;&#36753;&#12289;&#36134;&#21495;&#12289;&#35777;&#20070;&#12289;&#31614;&#21517;&#37197;&#32622;&#12289;SDK &#26412;&#22320;&#36335;&#24452;&#12289;&#35774;&#22791;&#31169;&#26377;&#21442;&#25968;&#25110;&#29983;&#20135;&#29615;&#22659;&#24120;&#37327;&#12290;

## &#35768;&#21487;&#35777;

MIT

</details>

---

<details>
<summary id="english"><strong>English</strong></summary>

## Overview

`arkts-project-skill` is a reusable Codex skill for HarmonyOS Stage-model ArkTS projects. It packages practical workflows for project recognition, safe editing boundaries, ArkUI state and lifecycle behavior, layered business implementation, platform capabilities, data handling, and risk-based verification.

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

Use the `skills` installer when possible. If you also use Git cloning or a manual copy, do not install the same skill into the same location twice. Node.js 18+ (including `npx`) is required.

### Quick Install (Recommended)

```bash
npx skills@latest add Yjx98/arkts-project-skill
```

### Specific Install: Codex Global

```bash
npx skills@latest add Yjx98/arkts-project-skill -a codex -g
```

`-a codex` targets Codex only. `-g` makes the skill available across projects. The quick-install command lets the `skills` CLI guide the installation scope.

### Update

```bash
npx skills@latest update arkts-project-skill -g
```

`npx` downloads and runs the latest `skills` CLI on demand, so a global npm package is not required. After installation, restart Codex or refresh skill discovery.

### Alternative: Git Install

If you do not use Node.js / npm, make sure `git` is installed first. You can verify it with `git --version`.

### macOS / Linux

```bash
mkdir -p ~/.codex/skills
git clone --depth 1 https://github.com/Yjx98/arkts-project-skill.git ~/.codex/skills/arkts-project-skill
```

Update to the latest version:

```bash
git -C ~/.codex/skills/arkts-project-skill pull --ff-only
```

### Windows PowerShell

```powershell
$skills = Join-Path $env:USERPROFILE ".codex\skills"
New-Item -ItemType Directory -Force -Path $skills
git clone --depth 1 https://github.com/Yjx98/arkts-project-skill.git (Join-Path $skills "arkts-project-skill")
```

Update to the latest version:

```powershell
git -C "$env:USERPROFILE\.codex\skills\arkts-project-skill" pull --ff-only
```

### Manual Install

Download this repository and copy the whole `arkts-project-skill` folder to:

```text
~/.codex/skills/arkts-project-skill
```

On Windows, the path is usually:

```text
%USERPROFILE%\.codex\skills\arkts-project-skill
```

## Example Prompts

- Use `use $arkts-project-skill` to implement an ArkUI page while preserving the existing project layering style.
- Use `use $arkts-project-skill` to decide how this HarmonyOS ArkTS change should be verified.
- Use `use $arkts-project-skill` to add permission handling, persistence, and async error handling.

## Repository Layout

```text
arkts-project-skill/
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- arkui-and-architecture.md
|   |-- platform-capabilities.md
|   `-- verification.md
|-- LICENSE
`-- README.md
```

## Scope

This skill captures reusable HarmonyOS engineering practice only. It does not include proprietary product logic, accounts, credentials, certificates, signing config, local SDK paths, private device parameters, or production constants.

## License

MIT

</details>
