# Warcraft III Visual Symbols / 魔兽争霸 III 视觉符号 Skill

## 中文

本仓库发布 `warcraft3-visual-symbols` Codex Skill，用于建立《魔兽争霸 III：混乱之治》和《冰封王座》的图片证据驱动视觉符号资料。Skill 将官方文字资料限定为名称、类别、阵营、战役归属和覆盖范围核验；视觉标签必须从对象图片中观察得到，并与图片证据和阻塞审计分开保存。

### 适用范围

- 角色：战役命名角色、英雄、可训练单位、召唤物、中立生物和战役专属单位。
- 建筑：四大种族生产、资源、科技、防御、主城建筑，以及具有独立模型的中立、战役专属、废墟和毁坏形态。
- 场景：官方战役主要地点、独特过场地点、主要地貌和阵营环境母题。

### 输出原则

- 主表使用 Markdown，按角色、建筑、场景分组。
- 每条记录使用叙事性标识、画风、标签、题材、色彩、场景、形态、尺度、独特标识、轮廓、材质、装备或构件。
- 叙事性标识放在最前，画风紧随其后；不使用姿态或构图、光照字段。
- 中英文标签逐项对应，独特标识至少包含三个对象特有的可见锚点。
- 不继承原游戏低清画质或动画建模风格；画风字段采用简写 `超写实，UE5，IMAX，ARRI ALEXA 65`。
- 图片链接、来源类型、图片类型和核验状态进入证据文件；无法确认的细节进入 `BLOCKED.md`。

### 使用

将 `warcraft3-visual-symbols` 目录放入 Codex Skills 目录，或在任务中调用 `$warcraft3-visual-symbols`。执行时先读取项目的 `work/PROGRESS.md`、`outputs/BLOCKED.md`、`outputs/coverage_audit.md` 和 `outputs/image_evidence.md`，从首个未完成阶段继续，并在使用浏览器核验图片后关闭页面。

### 目录

- `warcraft3-visual-symbols/SKILL.md`：Skill 入口与工作流程。
- `warcraft3-visual-symbols/references/schema.md`：字段、记录模板和审计清单。
- `warcraft3-visual-symbols/agents/openai.yaml`：Codex 界面元数据。

## English

This repository publishes the `warcraft3-visual-symbols` Codex Skill for an image-evidence-grounded visual symbol catalog covering *Warcraft III: Reign of Chaos* and *The Frozen Throne*. Official text is used only to confirm names, categories, factions, campaign membership, and coverage. Visual labels must come from observable image elements and remain separate from the evidence log and blocker audit.

### Scope

- Characters: named campaign characters, heroes, trainable units, summons, neutral creatures, and campaign-exclusive units.
- Buildings: production, resource, technology, defense, and town-center buildings for all four factions, plus independent neutral, campaign, ruin, and destroyed forms.
- Scenes: major official campaign locations, distinctive cutscene places, terrain types, and faction environment motifs.

### Output rules

- The main catalog is Markdown grouped into characters, buildings, and scenes.
- Each record contains Narrative Cue, Style, Tags, Theme, Color, Scene, Form, Scale, Distinctive Marks, Silhouette, Material, and Equipment or Components.
- Narrative Cue comes first and Style follows it. Pose or Composition and Lighting are omitted.
- Chinese and English tags correspond item by item. Distinctive Marks contain at least three object-specific visible anchors.
- Do not inherit low-resolution game rendering or animation-model artifacts. Use the compact style label `ultra-realistic, UE5, IMAX, ARRI ALEXA 65`.
- Image URLs, source type, media type, and verification state belong in the evidence log. Unconfirmed details belong in `BLOCKED.md`.

### Usage

Install the `warcraft3-visual-symbols` directory in a Codex Skills directory or invoke `$warcraft3-visual-symbols`. Before editing, read `work/PROGRESS.md`, `outputs/BLOCKED.md`, `outputs/coverage_audit.md`, and `outputs/image_evidence.md`; resume from the first unfinished stage and close the browser after each image review.

### Contents

- `warcraft3-visual-symbols/SKILL.md`: Skill entry point and workflow.
- `warcraft3-visual-symbols/references/schema.md`: Field schema, record template, and audit checklist.
- `warcraft3-visual-symbols/agents/openai.yaml`: Codex UI metadata.
