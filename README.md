# JIEKE AI Visual Tag Abstractor

## 中文

本仓库发布 `jieke-ai-visual-tag-abstractor` Codex Skill，用于把任意指定 IP 的角色、建筑、道具、载具、地点和场景图片整理为图片证据驱动的视觉符号资料。Skill 将官方文字资料限定为名称、类别、归属、故事或战役范围核验；视觉标签必须从对象图片中观察得到，并与图片证据和阻塞审计分开保存。Warcraft III 是已验证示例，不是适用范围限制。

### 适用范围

- 角色和生物：角色、英雄、单位、召唤物、首领和变体。
- 物体和建筑：建筑、道具、载具、机械、武器和具有独立模型的毁坏形态。
- 地点和场景：官方地点、独特过场地点、主要地貌和环境母题。

### 输出原则

- 主表使用 Markdown，按角色、建筑、场景分组。
- 每条记录使用叙事性标识、画风、标签、题材、色彩、场景、形态、尺度、独特标识、轮廓、材质、装备或构件。
- 叙事性标识放在最前，画风紧随其后；不使用姿态或构图、光照字段。
- 中英文标签逐项对应，独特标识至少包含三个对象特有的可见锚点。
- 不继承原游戏低清画质或动画建模风格；画风字段采用简写 `超写实，UE5，IMAX，ARRI ALEXA 65`。
- 图片链接、来源类型、图片类型和核验状态进入证据文件；无法确认的细节进入 `BLOCKED.md`。

### 使用

将 `jieke-ai-visual-tag-abstractor` 目录放入 Codex Skills 目录，或在任务中调用 `$jieke-ai-visual-tag-abstractor`。执行时先读取项目的 `work/PROGRESS.md`、`outputs/BLOCKED.md`、`outputs/coverage_audit.md` 和 `outputs/image_evidence.md`，从首个未完成阶段继续，并在使用浏览器核验图片后关闭页面。

### 版权与使用风险

图片只用于观察可见元素，不逐像素复刻原图，也不把生成结果描述为官方作品。指定 IP 的名称、角色、标志、纹章、服装和场景可能受版权或商标保护；公开发布、商业使用或用于衍生作品前，应核对权利方条款并在需要时取得许可。不要要求或保留在世艺术家的可识别个人画风。无法确认权利范围时，写入 `BLOCKED.md` 并改用通用视觉描述。

### 目录

- `jieke-ai-visual-tag-abstractor/SKILL.md`：Skill 入口与工作流程。
- `jieke-ai-visual-tag-abstractor/references/schema.md`：字段、记录模板和审计清单。
- `jieke-ai-visual-tag-abstractor/agents/openai.yaml`：Codex 界面元数据。

## English

This repository publishes the `jieke-ai-visual-tag-abstractor` Codex Skill, a reusable IP-agnostic workflow for turning reference images of characters, buildings, props, vehicles, places, and scenes into image-evidence-grounded visual symbol catalogs. Warcraft III is a validated example project, not the scope limit. Official text is used only to confirm names, categories, affiliation, story or campaign membership, and coverage.

### Scope

- Characters and creatures: named characters, heroes, units, summons, bosses, and variants.
- Objects and buildings: buildings, props, vehicles, machines, weapons, and independent destroyed forms.
- Places and scenes: official locations, distinctive cutscene places, terrain types, and environment motifs.

### Output rules

- The main catalog is Markdown grouped into characters, buildings, and scenes.
- Each record contains Narrative Cue, Style, Tags, Theme, Color, Scene, Form, Scale, Distinctive Marks, Silhouette, Material, and Equipment or Components.
- Narrative Cue comes first and Style follows it. Pose or Composition and Lighting are omitted.
- Chinese and English tags correspond item by item. Distinctive Marks contain at least three object-specific visible anchors.
- Do not inherit low-resolution game rendering or animation-model artifacts. Use the compact style label `ultra-realistic, UE5, IMAX, ARRI ALEXA 65`.
- Image URLs, source type, media type, and verification state belong in the evidence log. Unconfirmed details belong in `BLOCKED.md`.

### Usage

Install the `jieke-ai-visual-tag-abstractor` directory in a Codex Skills directory or invoke `$jieke-ai-visual-tag-abstractor`. Before editing, read `work/PROGRESS.md`, `outputs/BLOCKED.md`, `outputs/coverage_audit.md`, and `outputs/image_evidence.md`; resume from the first unfinished stage and close the browser after each image review.

### Copyright and use risks

Use images to identify observable elements rather than reproducing protected artwork pixel for pixel. Do not claim official affiliation or endorsement. Names, logos, emblems, signature costumes, and settings from a chosen IP may remain copyrighted or trademarked; review the rights holder's terms and obtain permission where public, commercial, or derivative use requires it. Do not request or preserve a recognizable living artist's personal style. When rights or transformation boundaries are unclear, record the risk in `BLOCKED.md` and switch to generic visual language.

### Contents

- `jieke-ai-visual-tag-abstractor/SKILL.md`: Skill entry point and workflow.
- `jieke-ai-visual-tag-abstractor/references/schema.md`: Field schema, record template, and audit checklist.
- `jieke-ai-visual-tag-abstractor/agents/openai.yaml`: Codex UI metadata.
