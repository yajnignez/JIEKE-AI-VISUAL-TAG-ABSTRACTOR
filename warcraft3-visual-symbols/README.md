# Warcraft III Visual Symbols

## 中文

这是一个用于《魔兽争霸 III：混乱之治》和《冰封王座》视觉重构资料整理的 Codex Skill。它把官方名称与分类资料、逐对象图片证据、短视觉标签、场景地图描述、叙事性标识和阻塞审计组织成可复用流程，适合整理 Midjourney 等生图模型的视觉重构素材。Skill 名称为 `warcraft3-visual-symbols`。

### 能做什么

- 建立角色、建筑、官方战役场景三份内部清单。
- 按图片可见元素提取中英双语短标签。
- 为对象加入不重复场景的叙事性标识，让角色和建筑适合生成群像与行动画面。
- 用一句话压缩原作地图和环境母题。
- 记录图片链接、来源类型、图片类型和核验状态。
- 将无法确认的名称、版本、视觉差异和地图边界写入 `BLOCKED.md`。

### 主记录字段

每条记录按以下顺序输出：

`叙事性标识`、`画风`、`标签`、`题材`、`色彩`、`场景`、`形态`、`尺度`、`独特标识`、`轮廓`、`材质`、`装备或构件`。

删除 `姿态或构图` 和 `光照`，避免把生成画面固定成僵硬的资产展示。画风短标签统一为“超写实，UE5，IMAX，ARRI ALEXA 65”。每条记录的 `独特标识` 至少包含三个具体视觉锚点。角色英文段落不超过 950 字符，扩写叙事时优先压缩重复的普通标签。

### 证据原则

官方文字资料只确认名称、类别、阵营、战役归属和覆盖范围。视觉标签必须有图片依据。图片链接、来源类型、对象对应关系和核验状态只放在 `image_evidence.md`，不放入主表。不能从图片确认的细节写入 `BLOCKED.md`，不得用想象内容伪装成原作事实。

### 目录

- `SKILL.md`：Skill 入口和执行规则。
- `references/schema.md`：主表字段、记录模板和审核清单。
- `agents/openai.yaml`：Codex 界面显示信息。

### 使用方式

将 `warcraft3-visual-symbols` 目录放入 Codex 的 Skills 目录，或在任务中使用 `$warcraft3-visual-symbols` 显式引用该 Skill。执行时先读取已有 `work/PROGRESS.md`，再从未完成阶段继续；不要重复覆盖已经核验的样本。

## English

This Codex Skill organizes image-grounded visual reconstruction research for *Warcraft III: Reign of Chaos* and *The Frozen Throne*. It combines official name and coverage checks, per-object image evidence, bilingual short tags, one-sentence map descriptions, narrative cues, and blocker auditing for Midjourney-style visual reconstruction workflows.

### Capabilities

- Maintain internal lists for characters, buildings, and official campaign scenes.
- Extract bilingual short labels from visible image elements.
- Add narrative cues that describe action and relationships without repeating the scene field.
- Compress original map environments and scene motifs into one sentence.
- Track image links, source type, image type, and verification state.
- Record uncertain names, versions, model differences, and map boundaries in `BLOCKED.md`.

### Main record fields

Records use this order:

`Narrative Cue`, `Style`, `Tags`, `Theme`, `Color`, `Scene`, `Form`, `Scale`, `Distinctive Marks`, `Silhouette`, `Material`, and `Equipment or Components`.

`Pose or Composition` and `Lighting` are removed so the output does not force a rigid asset-display pose. The compact style label is `ultra-realistic, UE5, IMAX, ARRI ALEXA 65`. Every record needs at least three concrete object-specific anchors in `Distinctive Marks`. A role's English section must stay at or below 950 characters; shorten repeated ordinary tags before shortening the narrative.

### Evidence policy

Official text confirms names, categories, factions, campaign membership, and coverage only. Visual labels require image evidence. Image links, source type, object mapping, and verification state belong in `image_evidence.md`, not in the main symbol file. Details that cannot be confirmed from an image belong in `BLOCKED.md` and must not be presented as canon facts.

### Contents

- `SKILL.md`: Skill entry point and operating rules.
- `references/schema.md`: Field schema, record template, and review checklist.
- `agents/openai.yaml`: Codex UI metadata.

### Usage

Place the `warcraft3-visual-symbols` directory in a Codex Skills directory, or invoke it as `$warcraft3-visual-symbols`. Start by reading `work/PROGRESS.md` and continue from the first unfinished stage; do not overwrite already verified samples.
