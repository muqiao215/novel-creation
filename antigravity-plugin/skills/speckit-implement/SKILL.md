---
name: speckit-implement
description: Execute the novel drafting and polishing plan by writing chapters and managing narrative artifacts defined in tasks.md.
---

## User Input

The user's input for this invocation is the text they typed after `/speckit-implement`. It may be empty.
You **MUST** consider user input before proceeding.

## Outline

1. Run `.specify/scripts/bash/check-prerequisites.sh --json --require-tasks --include-tasks` from repo root and parse FEATURE_DIR and AVAILABLE_DOCS list. All paths must be absolute.

2. **Check Literary Checklist Status** (if FEATURE_DIR/checklists/ exists):
   - Scan all checklist files in `checklists/`
   - If incomplete items exist, display summary and ask user whether to proceed.

3. **Load Narrative Context**:
   - **REQUIRED**: Read `tasks.md` for chapter execution order and specific clue goals.
   - **REQUIRED**: Read `plan.md` for narrative architecture, scene beats, and sensory palette.
   - **REQUIRED**: Read `characters.md` for character voices, Want vs Need, and psychological wounds.
   - **REQUIRED**: Read `timeline.md` for chronology, weather, and physical travel constraints.
   - **REQUIRED**: Read `foreshadowing.md` for Chekhov's guns and clue registry.

4. **Novel Drafting Execution Protocol (Chapter-by-Chapter)**:
   For each chapter task in `tasks.md`:
   - **Step 1: Anchor POV & Voice**:
     Lock the narrative POV. Ensure the narration never leaks thoughts or emotions of other characters unless perceived through external sensory evidence.
   - **Step 2: Check Timeline & Weather Matrix**:
     Verify current chapter's exact day, hour, physical environment, and distance to previous scene.
   - **Step 3: Execute the Scene Turn (McKee Scene & Sequel)**:
     Write the narrative ensuring a clear value state reversal:
     - Goal → Conflict → Unexpected Gap / Disaster
     - Or Reaction → Dilemma → Hard Decision
   - **Step 4: Weave Sensory Details (Show, Don't Tell)**:
     Replace abstract emotional summaries with concrete sensory stimuli (sounds, tactile textures, temperature, light, posture).
   - **Step 5: Plant or Pay Off Registered Clues**:
     Integrate designated clues from `foreshadowing.md` naturally into background details.
   - **Step 6: Anti-Cliché Sweep**:
     Ensure zero prohibited AI clichés ("倒吸凉气", "冷笑", "眼神闪烁") enter the manuscript.
   - **Step 7: Task Completion**:
     Mark the task as completed `[X]` in `tasks.md`.

5. **Progress Tracking**:
   - Report progress and character count after each chapter or milestone.
   - Update `foreshadowing.md` status if clues are advanced or resolved.
   - Summarize completed chapters and prompt for the next phase.
