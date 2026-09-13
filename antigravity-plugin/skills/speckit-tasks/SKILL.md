---
name: speckit-tasks
description: Generate an actionable, dependency-ordered tasks.md for novel drafting and polishing based on design artifacts.
---

## User Input

The user's input for this invocation is the text they typed after `/speckit-tasks`. It may be empty.
You **MUST** consider user input before proceeding.

## Outline

1. **Setup**: Run `.specify/scripts/bash/check-prerequisites.sh --json` from repo root and parse FEATURE_DIR and AVAILABLE_DOCS list. All paths must be absolute.

2. **Load design documents**: Read from FEATURE_DIR:
   - **Required**: `plan.md` (structure, scenes, beats), `spec.md` (premise, milestones, POV, voice)
   - **Literary Core Artifacts**: `characters.md` (Want vs Need, wounds, speech habits), `timeline.md` (chronology, travel times, weather), `foreshadowing.md` (Chekhov's guns inventory)

3. **Execute novel task generation workflow**:
   - Organize tasks by **Narrative Progression & Crafting Phases** (NOT software user stories!):
     1. **Phase 1: Narrative Anchors & Tracking Setup**
        - Verify/initialize `constitution.md`, `characters.md`, `timeline.md`, `foreshadowing.md`.
     2. **Phase 2 to 4: Chapter-by-Chapter Drafting & Scene Beats**
        - Group tasks by volume/act or logical chapter cluster.
        - For EACH chapter, define:
          - Scene Goal → Conflict → Disaster (McKee Scene Turn)
          - POV enforcement (zero head-hopping)
          - Specific clues to plant or advance (e.g. Plant FG-01, Advance FG-03)
          - Word count target and sensory focus
     3. **Setting Mutation & Impact Governance Phase (conditional / as needed)**
        - Tasks to audit setting changes, propagate diffs across 3 core tracking tables and chapters.
     4. **Phase 5: Climax & Foreshadowing Resolution**
        - Ensure every registered clue in `foreshadowing.md` has an explicit payoff task.
     5. **Phase 6: Master Literary Craft Polishing (Show Don't Tell, Subtext, Anti-Cliché)**
        - Show Don't Tell sweep (eliminate abstract emotional narration)
        - Subtext & dialogue tightening (Hemingway iceberg technique)
        - AI cliché & adverb purge
     6. **Phase 7: Final Consistency & Analytical Review**
        - `/speckit-analyze` execution for 6-dimensional literary audit.

4. **Generate tasks.md**: Use `.specify/templates/tasks-template.md` as structure. Fill with concrete chapter titles, specific clue IDs, exact file paths, and verifiable checkpoints.

5. **Report**: Output path to generated tasks.md and summary:
   - Total chapter count and planned word count
   - Key milestone checkpoints
   - Clue tracking coverage
   - Readiness for `/speckit-implement`.
