# LLM Operating Directives
This document defines mandatory behavioral rules for any LLM operating inside this repository.
These rules are non-negotiable and derived from SYSTEM_OVERVIEW.md.

## Bootstrap Exception (Critical)
If any file in the Mandatory Read Order is missing (common in a new repo):
1) Treat this as a Structural Change.
2) Prepare Doc Update Proposals to create the missing folders/files (minimum: placeholders).
3) Freeze and request explicit human approval.
4) After approval and creation, restart the Mandatory Read Order from step 1.
Do NOT request “clarification” for missing bootstrap files; request approval to create them.

## Mandatory Read Order
Before taking any action, the LLM MUST read the following files in order:
1. SYSTEM_OVERVIEW.md
2. Project_Overview.md
3. Context_Packet.md
4. Decision_and_Change_Log.md
5. Development_Stages.md
6. Task_Board.md
If any of these files are missing, empty, or unreadable, the LLM MUST stop and request clarification.

## Stop Conditions
The LLM MUST immediately stop and request explicit human input if:
- A documentation change is required or implied.
- A structural change is implied.
- A decision affecting scope, direction, assumptions, or constraints is identified.
- The next step is ambiguous.
- Conflicting instructions or signals are detected.

## Proposal-Only Zones
The following actions are strictly proposal-only:
- Documentation changes
- Stage changes
- Architectural or system decisions
- Workflow restructuring
The LLM MUST NOT implement these changes without explicit approval.

## Context vs Decision Enforcement
- Context_Packet.md may only reflect approved decisions.
- Decision_and_Change_Log.md MUST be updated before Context_Packet.md.
- A decision does not exist unless it is logged.

## Allowed Actions Without Approval
Without human approval, the LLM may ONLY:
- Ask clarification questions.
- Summarize existing documents.
- Identify inconsistencies.
- Prepare Doc Update Proposals.
Any other action requires explicit approval.
