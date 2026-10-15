---
name: jieke-ai-visual-tag-abstractor
description: Build or audit image-grounded visual symbol catalogs for characters, objects, buildings, and scenes from a named IP, with bilingual short tags, narrative cues, evidence tracking, and copyright-aware reconstruction boundaries.
metadata:
  short-description: Abstract image-grounded visual tags for named IPs
---

# JIEKE AI Visual Tag Abstractor

Use this skill when the task is to build, revise, or audit an image-grounded visual reference catalog for a named IP. It supports characters, creatures, props, vehicles, buildings, locations, environments, and scene motifs. Warcraft III is one example, not the scope boundary. It produces reconstruction references, not lore summaries or full image prompts.

## Workflow

1. Read the existing progress file, blocker file, coverage audit, evidence log, and internal lists before editing. Resume from the first unfinished stage.
2. Build internal lists that match the requested IP and record original name, category, affiliation or location, source, version, and whether the object has an independent visual model.
3. Use official text only to confirm names, categories, affiliation, story or campaign membership, and coverage. Use at least one image per object for visual tags. Record page URL, image URL, source type, image type, object, and verification state in `image_evidence.md`; do not put links in the main symbol file.
4. Observe each object independently from its corresponding image. Open one image, inspect it, record the evidence, and close the browser page before moving to the next object. Do not infer one object's labels from another object's template, faction palette, or global consistency rules.
5. Observe visible elements only. Do not inherit low-resolution rendering, animation-model artifacts, a source image's global art style, or a recognizable artist's signature. Prefer full-body or full-structure evidence, equipment, silhouette, and interaction with the environment; avoid face-close-up language. If a detail cannot be confirmed, write it to `BLOCKED.md` and omit it or mark it as provisional.
6. Write the requested Markdown catalog grouped by the object classes defined by the project. Keep names and classifications faithful to the selected IP, while allowing visual reconstruction to change materials, lighting, detail, scale, and composition.

## Main record format

Each record uses this order in both languages:

1. `Narrative Cue / 叙事性标识`
2. `Style / 画风`
3. `Tags / 标签`
4. `Theme / 题材`
5. `Color / 色彩`
6. `Scene / 场景`
7. `Form / 形态`
8. `Scale / 尺度`
9. `Distinctive Marks / 独特标识`
10. `Silhouette / 轮廓`
11. `Material / 材质`
12. `Equipment or Components / 装备或构件`

Do not add `Pose or Composition` or `Lighting`. Keep each bilingual item paired in the same order. Use short, copyable phrases separated by Chinese commas or English commas. Keep the English section of a role record at or below 950 characters; when expanding the narrative, shorten repeated non-narrative tags first.

`Style` is concise and fixed: `超写实，UE5，IMAX，ARRI ALEXA 65` / `ultra-realistic, UE5, IMAX, ARRI ALEXA 65`.

## Label rules

- `Narrative Cue` comes first and carries the scene action: who is doing what, with whom, during what process, and with what result. It may describe a group, but it must not repeat the `Scene` sentence or pretend to be verified original-game plot.
- For a character or building, `Scene` is a one-sentence visual description of the corresponding original environment. Do not use a campaign, city, or map proper name in that field.
- Use the project's compressed one-sentence scene descriptions as the only scene reference for later character records; the narrative cue and scene sentence must not repeat each other.
- Make narrative cues concrete and varied: describe a whole figure or group performing an action, handling equipment, responding to terrain, or changing a local situation. Narrative cues are generation guidance, not unverified plot claims.
- For a scene record, `Tags` is the compressed one-sentence map description. Keep terrain, landmarks, and activity state visible and concrete.
- `Distinctive Marks` must contain at least three object-specific anchors such as weapon structure, head ornament, body proportion, clothing layers, roof or spire geometry, door or window form, motif, or landmark. Do not fill it with faction color alone.
- Remove duplicate phrases between `Tags`, `Form`, and `Distinctive Marks`; leave the most specific wording in `Distinctive Marks`.
- Do not force a player-slot color. Use visible structural colors and object colors; omit replaceable faction-color instructions.
- Avoid abstract words such as “mysterious,” “epic,” or “dark” unless attached to visible form, material, color, lighting, or composition.
- When an IP has multiple releases, treat later or remastered imagery as supplemental unless the project explicitly selects it. Preserve recognizable silhouettes and symbols while separating visible identity from source rendering style.

## Copyright and use boundaries

- Use reference images to identify observable visual elements, not to reproduce a protected image pixel for pixel.
- Treat image access as separate from reuse permission: check the source image's copyright, license, site terms, and any publicity or brand restrictions.
- Do not claim affiliation, endorsement, or official status. Keep source URLs and licensing notes in the evidence or audit files.
- Character names, logos, emblems, distinctive costumes, and settings may remain protected or trademarked even when the output is newly rendered. For public or commercial work, check the IP owner's terms and obtain permission or a suitable license where required.
- Do not request or preserve a named living artist's signature style. Describe neutral production properties such as lens, material, lighting, rendering pipeline, and composition instead.
- This workflow is not legal advice. When the intended use, rights status, or degree of transformation is unclear, record the risk in `BLOCKED.md`, use generic visual language, and pause high-risk public or commercial use until reviewed.

## 版权与使用边界

- 图片仅用于识别可见视觉元素，不逐像素复刻受保护图片。
- 图片可访问不等于获得再利用许可；应单独核对图片版权、许可证、站点条款以及肖像或品牌限制。
- 不宣称官方关联、授权或背书；图片来源和许可信息只放入证据或审计文件。
- 角色名称、标志、纹章、独特服装和世界观设定可能仍受版权或商标保护。公开发布或商业使用前，应检查权利方条款，必要时取得授权或合适许可。
- 不要求或保留在世艺术家的可识别个人画风；改用镜头、材质、光线、渲染管线和构图等中性的制作属性。
- 本流程不构成法律意见。用途、权利状态或改造程度无法确认时，写入 `BLOCKED.md`，先使用通用且不指向受保护标识的视觉描述，并暂停高风险公开或商业使用。

## Evidence and blockers

`image_evidence.md` is an audit log, not a prompt source. A direct image link is not the same as visual confirmation. Keep these states distinct: verified by image observation, link obtained but awaiting observation, missing direct image, and retrieval failure. Put uncertain names, version ownership, model differences, scene boundaries, and unconfirmed visual details in `BLOCKED.md` with the reason, sources checked, and temporary handling.

## Required deliverables

- `outputs/<visual_symbols>.md`
- `outputs/image_evidence.md`
- `outputs/coverage_audit.md`
- `outputs/BLOCKED.md`
- `work/PROGRESS.md`

Before finishing, verify counts against the internal lists, confirm every record has six core dimensions plus `Distinctive Marks`, check bilingual ordering, check that no removed pose or lighting fields remain, and run a random duplicate-signature review for each object class. Never generate Excel, SQLite, SQL, or another database when the requested main file is Markdown.
