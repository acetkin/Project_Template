# Project Documentation Rules
This document defines mandatory rules for all project documentation in this repository.
These rules are binding for both humans and LLMs.

## Scope
These rules apply to all files under the /_docs directory except SYSTEM_OVERVIEW.md and instruction-level documents.

## Language
- All project documentation MUST be written in English.
- No bilingual or mixed-language documents are allowed.

## Structural Authority
- Documentation structure is defined in SYSTEM_OVERVIEW.md.
- No document may introduce new sections, folders, or files outside the defined structure.
- Structural changes require explicit human approval.

## 3×3 Documentation Constraint
For all documents under /_docs/A_Overview/:
- Each document MUST follow a strict 3×3 structure.
- Exactly three main sections are allowed.
- Each section MUST contain exactly three bullet points.
- Each bullet point MUST be self-contained.
- Bullet points MAY contain multiple sentences.
- Bullet points MUST NOT rely on previous or subsequent bullets.

## Content Discipline
- Documentation describes intent, structure, and rationale.
- Documentation MUST NOT include implementation details.
- Documentation MUST NOT include speculative or future content unless explicitly marked and approved.
- Documentation MUST NOT duplicate content from other documents.

## Modification Rules
- No documentation may be modified without explicit human approval.
- All proposed changes MUST follow the Documentation Update Protocol.
- Silent edits are strictly forbidden.

## Consistency Rules
- Terminology MUST be consistent across all documents.
- If a term changes meaning, the change MUST be logged as a decision.
- Contradictions MUST be reported immediately and resolved before proceeding.

## Enforcement
- If any rule in this document is violated, the LLM MUST stop.
- The LLM MUST report the violation and propose a correction.
- No automatic fixes are allowed without approval.
