---
name: speckit-clarify
description: Identify underspecified dramatic stakes, character motivations, and narrative gaps in the novel spec by asking targeted literary clarification questions.
---

## User Input

The user's input specifies clarification focus (e.g. character psychology, mystery mechanics, pacing). It may be empty.
You **MUST** consider user input before proceeding.

## Outline

Goal: Act as a master story editor (麦基/特鲁比式资深文学策划) to detect and resolve dramatic ambiguities, shallow motivations, or causal plot holes before planning.

Execution steps:

1. Run `.specify/scripts/bash/check-prerequisites.sh --json --paths-only` from repo root. Parse `FEATURE_DIR` and `FEATURE_SPEC`.

2. Load the current novel `spec.md`. Perform an editorial scan across the **Five Literary Pillars**:

   **1. 危机与不可逆代价 (Stakes & Reversibility)**:
   - 若主角失败，代价是否致命且不可逆？
   - 外部时限（Ticking Clock）是否足够紧迫？

   **2. 人物欲望与道德需要 (Want vs. Moral Need)**:
   - 主角的外在追求（Want）与内心深层的道德盲区（Need）是否清晰对立？
   - 主角坚信的“谎言”（The Lie）是否在故事中受到根本性挑战？

   **3. 对手的悲剧性与动机深度 (Antagonist Dimensions)**:
   - 主要对手是脸谱化恶人，还是怀揣自身创伤与信仰的镜像人物？
   - 对手的每一次阻击是否具备令人信服的心性必然性？

   **4. 因果机制与伏笔公平性 (Causal Integrity & Fair Play)**:
   - 核心反转或高潮破局是否具备现实物理常识？是否存在机械降神风险？
   - 关键线索是否在前文有前置空间？

   **5. 叙事视角与文风语域 (POV & Voice Boundaries)**:
   - POV视点是否绝对清晰，杜绝无意间的全知越界（Head-hopping）？
   - 时代语调与五感基调是否统一？

3. Generate prioritized candidate clarification questions (maximum 5, one at a time):
   - Formulate questions from the story editor's perspective.
   - For each question, offer 2–3 dramatically compelling choices + custom write-in option.
   - Present a clear **Recommended Option** with literary reasoning.

4. On receiving the author's decision:
   - Record the decision under `## Clarifications` in `spec.md`.
   - Propagate the updated character motivation or plot mechanic to relevant sections of `spec.md`.

5. Output summary of resolved literary ambiguities and suggest proceeding to `/speckit-plan`.
