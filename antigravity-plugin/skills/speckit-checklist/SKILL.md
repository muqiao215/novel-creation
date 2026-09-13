---
name: speckit-checklist
description: Generate master craft literary checklists for novel chapters, scenes, and character consistency.
---

## Checklist Purpose: "Unit Tests for Literary Craft"

Checklists in novel creation are **QUALITY AUDITS FOR NARRATIVE ARTISTRY** — validating that scenes, characters, dialogues, and descriptions meet master-level creative writing standards.

## User Input

The user's input specifies the focus domain (e.g. `show-dont-tell`, `scene-turn`, `subtext`, `character`, `pacing`). If empty, infer the most critical current phase from the project state.

## Execution Steps

1. Run `.specify/scripts/bash/check-prerequisites.sh --json` from repo root.

2. Load feature context from `FEATURE_DIR`: `spec.md`, `plan.md`, `characters.md`, `foreshadowing.md`.

3. Generate a dedicated literary checklist in `FEATURE_DIR/checklists/[domain].md`.

## Canonical Literary Checklist Domains & Items

### 1. 感官显影清单 (`show-dont-tell.md`)
- [ ] CHK001 - 是否已将所有抽象情绪定性词（愤怒、悲伤、惊恐）替换为具象生理反应（肌肉收缩、瞳孔变化、呼吸速率、喉结吞咽）？
- [ ] CHK002 - 场景中是否调动了视觉以外的两种以上感官（温度感、气味、触感、环境底噪）？
- [ ] CHK003 - 动作描写是否由强有力的精确动词主导，且已完全剔除空泛无力的副词？
- [ ] CHK004 - 环境白描是否承担了“烘云托月”的功能，投射出人物此刻的隐秘心境？

### 2. 场景转折与节拍清单 (`scene-turn.md`) - McKee Scene Turn
- [ ] CHK010 - 本场景主角开场时是否有清晰、具体、可感知的行动目标（Goal）？
- [ ] CHK011 - 主角在追求目标的过程中，是否遭遇了预料之外的现实阻力与鸿沟（The Gap）？
- [ ] CHK012 - 场景结尾处，人物在核心价值维度（如希望/绝望、坦诚/猜忌、胜算/危局）上是否发生了不可逆的极性反转？
- [ ] CHK013 - 是否存在通篇平铺直叙、仅交代信息的“死场景”？若有，是否已重构或删减？

### 3. 台词潜台词与冰山清单 (`subtext-dialogue.md`) - Hemingway Iceberg
- [ ] CHK020 - 核心对话是否避免了“心想即口说”（No "On-the-Nose" dialogue）？
- [ ] CHK021 - 人物在受到试探时，是否通过转移话题、沉默停顿、反问或肢体动作表现出抵触与掩饰？
- [ ] CHK022 - 台词用词与句式节奏是否严密契合该角色的社会阶层、身世教养与时代语域？
- [ ] CHK023 - 对话中是否暗藏双关、讽喻或只有知情读者能察觉的悬念隐语？

### 4. 人物心性与弧光清单 (`character-agency.md`) - Truby Want vs Need
- [ ] CHK030 - 人物的每一个抉择是否均由其核心欲望（Want）或过往创伤（Ghost）所驱动，而非作者意志的生硬安排？
- [ ] CHK031 - 人物是否在关键节点展现出不可妥协的性格底线或致命弱点？
- [ ] CHK032 - 配角与反派是否有其自洽的生存逻辑与悲剧根源，杜绝纯粹为了作恶而作恶的工具人化？

### 5. 节奏与悬念清单 (`pacing-suspense.md`)
- [ ] CHK040 - 章节结尾是否设置了强有力的悬置点（Hook / Cliffhanger），制造读者的急迫期待？
- [ ] CHK041 - 伏笔（Chekhov's Guns）的埋设是否足够隐蔽自然，既不显眼突兀，又能在后文回收时让读者感到“意料之外、情理之中”？
- [ ] CHK042 - 紧张激烈的动作场景与沉郁深思的反应续事（Sequel）之间，节奏张弛是否得当？

4. Save the checklist to `FEATURE_DIR/checklists/[domain].md` and output summary.
