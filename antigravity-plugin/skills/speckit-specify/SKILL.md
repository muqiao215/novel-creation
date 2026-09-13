---
name: speckit-specify
description: Create or update the novel specification from a natural language story premise or high concept.
---

## User Input

The user's input for this invocation is the text they typed after `/speckit-specify` in the triggering message. It represents the story premise, pitch, or core concept.

You **MUST** consider the user input before proceeding.

## Outline

1. Run the script `.specify/scripts/bash/create-new-feature.sh --json "<story premise>"` from repo root and parse its JSON output for BRANCH_NAME and SPEC_FILE. All file paths must be absolute.

2. Load `.specify/templates/spec-template.md` to understand the required novel specification structure.

3. Follow this novel-crafting execution flow:
   1. **Deconstruct Story Concept**:
      - Identify the Protagonist (Flaws, Backstory Wound/Ghost)
      - Identify the Inciting Incident (The event that breaks normal life)
      - Identify the Core Dramatic Question & Stakes (What happens if they fail?)
      - Identify Antagonism / Opponents (Forces preventing the goal)
   2. **Establish Theme & Moral Spectrum (McKee / Truby)**:
      - Positive Value vs. Negative Value vs. Contradictory Value
      - The Lie the protagonist believes vs. The Truth they must learn
   3. **Select Narrative POV & Literary Aesthetics**:
      - POV: Strict 3rd person limited / 1st person / Multi-POV rules
      - Sensory Palette: Central motifs, period texture, lighting, smell, touch
      - Prohibited tropes (Anti-Patterns): Ban AI clichés and abstract emotional exposition
   4. **Map Story Milestones**:
      - Inciting Incident (10%), Lock-in / Act I Break (25%), Midpoint / Mirror Moment (50%), Dark Night of the Soul (75%), Climax & Showdown (85-90%), Resolution (95-100%)
   5. **Define Acceptance Criteria**:
      - Causal integrity, character agency, scene vitality, foreshadowing closure

4. Write the novel specification to `SPEC_FILE` using the template structure, filling each section with rich, evocative creative detail.

5. **Novel Specification Quality Validation**:
   Generate `FEATURE_DIR/checklists/requirements.md` using this literary quality checklist:

   ```markdown
   # Novel Specification Quality Checklist: [BOOK NAME]
   
   **Purpose**: Validate novel premise, dramatic tension, and structural integrity before planning
   
   ## Literary Concept & Premise
   - [ ] Logline contains: protagonist flaw, inciting event, core conflict, and fatal stakes
   - [ ] Moral dilemma defined with clear positive/negative value spectrum
   - [ ] Protagonist's Lie and Truth clearly contrasted
   
   ## Narrative Voice & Style
   - [ ] POV clearly chosen with strict boundaries (no accidental head-hopping)
   - [ ] Sensory motifs (light, sound, smell, texture) established
   - [ ] Prohibited AI clichés and tropes explicitly listed
   
   ## Dramatic Architecture & Milestones
   - [ ] Target chapter count and word count clearly defined
   - [ ] Core dramatic question is specific and unresolved
   - [ ] Key milestones (Inciting, Midpoint, Climax) mapped with value turns
   - [ ] No [NEEDS CLARIFICATION] markers remain
   ```

6. Report completion with branch name, spec file path, and readiness for `/speckit-plan`.
