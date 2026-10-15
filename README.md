# JIEKE AI Visual Tag Abstractor

## 中文

这是一个保留 JIEKE 标识的通用 Codex Skill，用于把任意指定 IP 的角色、建筑、道具、载具、地点和场景图片整理为可用于 Midjourney 等生图模型的视觉符号资料。Warcraft III 只是已验证的示例项目，Skill 名称为 `jieke-ai-visual-tag-abstractor`。

### 能做什么

- 按项目建立角色、建筑、道具、载具、地点和场景等内部清单。
- 按图片可见元素提取中英双语短标签。
- 为对象加入不重复场景的叙事性标识，让角色和建筑适合生成群像与行动画面。
- 后续对象逐条独立核验：一次打开一张图，观察后关闭页面；优先整体形象、装备、轮廓和环境互动，减少面部特写。
- 用一句话压缩 IP 地图、地点和环境母题。
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

将 `jieke-ai-visual-tag-abstractor` 目录放入 Codex 的 Skills 目录，或在任务中使用 `$jieke-ai-visual-tag-abstractor` 显式引用该 Skill。执行时先读取已有 `work/PROGRESS.md`，再从未完成阶段继续；不要重复覆盖已经核验的样本。

### 版权与使用风险

图片只用于观察可见元素，不逐像素复刻原图，也不把生成结果描述为官方作品。图片本身的版权、授权范围、站点使用条款和人物/品牌权利仍需单独核对；“可访问”不等于“可再利用”。指定 IP 的名称、角色、标志、纹章、独特服装和场景可能受版权、商标或其他专有权保护。公开发布、商业使用、广告、游戏资产或衍生作品前，应核对权利方条款并在需要时取得许可；本 Skill 不提供法律意见。不要要求或保留在世艺术家的可识别个人画风。无法确认权利范围时，写入 `BLOCKED.md`，保留通用视觉描述并暂停高风险用途。

## English

This Codex Skill keeps the JIEKE identity while providing a reusable, IP-agnostic workflow for turning reference images of characters, buildings, props, vehicles, places, and scenes into visual symbol catalogs for Midjourney-style reconstruction. Warcraft III is a validated example project, not the scope limit. The Skill name is `jieke-ai-visual-tag-abstractor`.

### Capabilities

- Maintain internal lists for the object classes requested by the selected IP.
- Extract bilingual short labels from visible image elements.
- Add narrative cues that describe action and relationships without repeating the scene field.
- Verify later objects independently, opening one image at a time and closing it after observation; prefer whole figures, equipment, silhouettes, and environmental interaction over face close-ups.
- Compress map, location, and environment motifs into one sentence.
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

Place the `jieke-ai-visual-tag-abstractor` directory in a Codex Skills directory, or invoke it as `$jieke-ai-visual-tag-abstractor`. Start by reading `work/PROGRESS.md` and continue from the first unfinished stage; do not overwrite already verified samples.

### Copyright and use risks

Use images to identify observable elements rather than reproducing protected artwork pixel for pixel. The image's own copyright, license, site terms, and publicity or brand rights still require separate review; accessibility does not grant reuse permission. Do not claim official affiliation or endorsement. Names, logos, emblems, distinctive costumes, and settings from a chosen IP may remain protected by copyright, trademark, or other proprietary rights. Before public release, commercial use, advertising, game assets, or derivative work, review the rights holder's terms and obtain permission where required; this Skill is not legal advice. Do not request or preserve a recognizable living artist's personal style. When rights or transformation boundaries are unclear, record the risk in `BLOCKED.md`, keep the visual language generic, and pause high-risk use.
