---
name: warcraft3-visual-symbols
description: Build or audit an image-grounded Warcraft III visual symbol catalog for Reign of Chaos and The Frozen Throne, with bilingual short tags, scene-grounded narrative cues, and evidence/blocker tracking.
metadata:
  short-description: Create image-grounded Warcraft III visual symbol catalogs
---

# Warcraft III Visual Symbols

Use this skill when the task is to build, revise, or audit an image-grounded visual reference catalog for the original Warcraft III campaigns, units, heroes, summons, buildings, or official campaign scenes. It is for visual reconstruction references, not lore summaries or full image prompts.

## Workflow

1. Read the existing progress file, blocker file, coverage audit, evidence log, and internal lists before editing. Resume from the first unfinished stage.
2. Build or update three internal lists: characters, buildings, and scenes. Each row records the original Chinese and English name, category, faction or location, source, version, and whether it has an independent visual model.
3. Use official text only to confirm names, categories, factions, campaign membership, and coverage. Use at least one image per object for visual tags. Record page URL, image URL, source type, image type, object, and verification state in `image_evidence.md`; do not put links in the main symbol file.
4. Observe the image for visible elements only. Do not inherit low-resolution game rendering, animation-model artifacts, or a source image's overall art style. If a detail cannot be confirmed, write it to `BLOCKED.md` and omit it or mark it as provisional.
5. Write the main file as Markdown grouped under `角色`, `建筑`, and `场景`. Preserve official names and the original four-faction identity. The Demon Hunter is `暗夜精灵 / Night Elf`.

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
- For a scene record, `Tags` is the compressed one-sentence map description. Keep terrain, landmarks, and activity state visible and concrete.
- `Distinctive Marks` must contain at least three object-specific anchors such as weapon structure, head ornament, body proportion, clothing layers, roof or spire geometry, door or window form, motif, or landmark. Do not fill it with faction color alone.
- Remove duplicate phrases between `Tags`, `Form`, and `Distinctive Marks`; leave the most specific wording in `Distinctive Marks`.
- Do not force a player-slot color. Use visible structural colors and object colors; omit replaceable faction-color instructions.
- Avoid abstract words such as “mysterious,” “epic,” or “dark” unless attached to visible form, material, color, lighting, or composition.
- Reforged imagery is a supplemental reference only when it clearly differs from the classic model. Prefer classic silhouettes and symbols.

## Evidence and blockers

`image_evidence.md` is an audit log, not a prompt source. A direct image link is not the same as visual confirmation. Keep these states distinct: verified by image observation, link obtained but awaiting observation, missing direct image, and retrieval failure. Put uncertain names, version ownership, model differences, scene boundaries, and unconfirmed visual details in `BLOCKED.md` with the reason, sources checked, and temporary handling.

## Required deliverables

- `outputs/wc3_visual_symbols.md`
- `outputs/image_evidence.md`
- `outputs/coverage_audit.md`
- `outputs/BLOCKED.md`
- `work/PROGRESS.md`

Before finishing, verify counts against the internal lists, confirm every record has six core dimensions plus `Distinctive Marks`, check bilingual ordering, check that no removed pose or lighting fields remain, and run a random duplicate-signature review for each object class. Never generate Excel, SQLite, SQL, or another database when the requested main file is Markdown.
