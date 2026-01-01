# SYSTEM OVERVIEW (Project System)

This document defines the operating system for starting and running any project in this repository. It is NOT a project document; it is the ruleset that a VS Code LLM must follow.

## Language
- All files in the repository MUST be written in English.
- Human communication may be in Turkish or English.

## Source of Truth
- This document is the single source of truth for workflow and structure.
- If any instruction conflicts with this document, this document prevails.

## Human Approval Policy (CRITICAL)
- The LLM MUST NOT create, edit, rename, or delete project documentation without explicit human approval.
- The LLM MAY propose changes only via a Doc Update Proposal.
- Changes are applied only after explicit approval.

## Project Docs Generation Policy
- This chat environment never creates or edits project documentation.
- All project documentation is created and maintained inside VS Code.

## Required Project Documentation Structure
When bootstrapping a new project, the LLM must create the following structure under `/_docs`:

```
_docs
  SYSTEM_OVERVIEW.md

  A_Overview/
    Project_Overview.md
    A_Design/
      A_Design.md
      A1_Features.md
      A2_System_Architecture.md
      A3_Interaction_Design.md
    B_Development/
      B_Development.md
      B1_Tech_Stack.md
      B2_Architecture.md
      B3_External_Services.md
    C_Marketing/
      C_Marketing.md
      C1_Positioning.md
      C2_Go_To_Market.md
      C3_Revenue_Model.md

  B_Operation/
    A_Instructions/
      Project_Documentation_Rules.md
      LLM_Operating_Directives.md
      Documentation_Update_Protocol.md
    B_Stages/
      Development_Stages.md
      Stage_Change_Logs.md
      Stage_Exit_Checklists.md
    C_Tasks/
      Task_Backlog.md
      Task_Board.md
      Release_Checklist.md

  C_Communication/
    Context_Packet.md
    Handoff_Protocol.md
    Decision_and_Change_Log.md
```
## Context and Decision Coupling Rule
- Context_Packet.md contains the current working mental model of the project.
- Decision_and_Change_Log.md records irreversible or direction-changing decisions.
Rules:
- Any decision that changes direction, scope, constraints, or assumptions MUST be logged in Decision_and_Change_Log.md.
- Context_Packet.md MUST be updated to reflect the latest approved decisions.
- A decision does not exist unless it is logged.
- Order of Operations:
1. Log the decision in Decision_and_Change_Log.md.
2. Update Context_Packet.md to reflect the approved decision.

## Documenting Rules (3×3 Constraint)
For all project documents under `/_docs/A_Overview/`:
- `Project_Overview.md` MUST contain exactly three main sections:
  - A. Design
  - B. Development
  - C. Marketing
- A strict 3×3 structure is mandatory:
  - Each subsection contains exactly three bullet points.
  - Each bullet point is self-contained and may include multiple sentences.

## Stage Files Roles
- `Development_Stages.md`: defines objectives, scope, and exit criteria for each stage.
- `Stage_Change_Logs.md`: records only changes made to stages (what, why, when).
- `Stage_Exit_Checklists.md`: defines operational completion checks for stages.

## Task Files Roles
- `Task_Backlog.md`: unordered list of tasks and ideas.
- `Task_Board.md`: task status tracking.
- `Release_Checklist.md`: final checklist for stage or release completion.

## Document Behavior Classification
All project documents fall into one of the following behavior categories:

- Directive Documents
  - Define rules and must remain stable.
  - Changes are rare and require explicit justification.
  - Include SYSTEM_OVERVIEW.md and all files under /_docs/B_Operation/A_Instructions/.

- State Documents
  - Represent the current operational or mental state.
  - Must always reflect the latest approved state.
  - Overwritten on update.
  - Examples: Context_Packet.md.

- Log Documents
  - Record historical, irreversible events.
  - Append-only.
  - Entries must never be edited or removed.
  - Examples: Decision_and_Change_Log.md, Stage_Change_Logs.md.

- Operational Documents
  - Track progress, tasks, and checklists.
  - May grow over time but follow strict formats.
  - Examples: Task_Backlog.md, Task_Board.md, Release_Checklist.md.


## Bootstrapping Procedure (VS Code LLM)

When starting a new project:

1) Read this `SYSTEM_OVERVIEW.md` and treat it as the **single source of truth**.

2) Check whether the required `/_docs` structure and the **Mandatory Read Order** files exist.
   - If anything is missing, treat this as a **Structural Change**.
   - Produce **Doc Update Proposals** to create the missing folders/files (at minimum as placeholders).
   - **STOP and request explicit human approval** before creating any folders/files.

3) After the required structure/files exist (or have been created with approval), re-run the **Mandatory Read Order** and proceed with documentation work.

4) Use the user-provided **Initial Prompt** as the project brief.
   - Produce **Doc Update Proposals** (ONLY proposals; no edits) to draft initial documentation content.
   - For EACH file, **STOP and request explicit human approval** before writing or editing that file.

5) Enforce coupling:
   - Any scope/direction/constraint change must be proposed in `Decision_and_Change_Log.md` **first**,
   - then reflected in `Context_Packet.md`.

6) After documentation is approved and written:
   - propose development stages (if needed),
   - then propose tasks (backlog + board),
   - then proceed to code tasks **only after approvals**.

7) Never commit, push, rename, or delete files unless explicitly requested by the user.


## Doc Update Proposal Format
When proposing documentation changes, always provide:
- File
- Section
- Old text
- Proposed text
- Rationale
- Requires approval: YES

## Change Type Matrix

All changes fall into one of the following categories:
1. Documentation Content Change
   - Affects: Any file under /_docs
   - Action: Doc Update Proposal REQUIRED
   - Human Approval: REQUIRED
2. Structural Change
   - Affects: Folder structure, file names, document hierarchy
   - Action: Explicit Proposal + Rationale
   - Human Approval: REQUIRED (before any action)
3. Stage Change
   - Affects: Development_Stages.md, Stage_Change_Logs.md
   - Action: Stage Change Proposal
   - Human Approval: REQUIRED
4. Task Change
   - Affects: Task_Backlog.md, Task_Board.md
   - Action: Edit allowed ONLY after explicit user confirmation
   - Human Approval: REQUIRED

No other change types are permitted.

## Proposal Lifecycle
All documentation changes follow this lifecycle:
1. Propose
   - LLM presents a Doc Update Proposal.
   - No file is modified.
2. Freeze
   - LLM halts all related actions.
   - Waits for explicit human approval.
3. Apply
   - Only after approval, the LLM applies the change in VS Code.
