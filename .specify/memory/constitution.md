<!-- SYNC IMPACT REPORT
Version change: N/A -> 1.0.0
Modified principles: N/A (new constitution)
Added sections: All sections (new constitution)
Removed sections: N/A
Templates requiring updates: 
- ✅ .specify/templates/plan-template.md - Updated to align with ADIT principles
- ✅ .specify/templates/spec-template.md - Updated to align with ADIT requirements
- ✅ .specify/templates/tasks-template.md - Updated to reflect ADIT task types
Templates pending updates: None
Follow-up TODOs: None
-->

# ADIT Preparation Book Constitution
<!-- Example: Spec Constitution, TaskFlow Constitution, etc. -->

## Core Principles

### I. Comprehensive Coverage
<!-- Example: Library-First -->
Every knowledge domain from the official study plan must be thoroughly covered with equal depth and accuracy; All 25 domains must be treated with equal importance; Each domain should include theoretical concepts, practical examples, and real-world applications relevant to the Assistant Director IT role.
<!-- Example: Every feature starts as a standalone library; Libraries must be self-contained, independently testable, documented; Clear purpose required - no organizational-only libraries -->

### II. Quality Assurance (NON-NEGOTIABLE)
<!-- Example: CLI Interface -->
Every chapter, assessment, and content element must undergo rigorous quality checks; All content must be reviewed by subject matter experts; Accuracy, consistency, and readability are non-negotiable requirements; Multiple review cycles are mandatory before publication.
<!-- Example: Every library exposes functionality via CLI; Text in/out protocol: stdin/args → stdout, errors → stderr; Support JSON + human-readable formats -->

### III. Exam-Focused Approach (NON-NEGOTIABLE)
<!-- Example: Test-First (NON-NEGOTIABLE) -->
Content must be structured to prepare candidates for both competitive examinations and actual job responsibilities; Every concept should be presented with exam perspective in mind; Practice questions must mirror actual exam patterns and difficulty levels; Red-Green-Refactor cycle applied to question quality and effectiveness.
<!-- Example: TDD mandatory: Tests written → User approved → Tests fail → Then implement; Red-Green-Refactor cycle strictly enforced -->

### IV. Practical Application Focus
<!-- Example: Integration Testing -->
Focus areas requiring practical application: Real-world IT infrastructure scenarios, Security implementations, Project coordination examples, Technical support challenges, Administrative procedures; Each theoretical concept must be linked to practical job scenarios.
<!-- Example: Focus areas requiring integration tests: New library contract tests, Contract changes, Inter-service communication, Shared schemas -->

### V. Accessibility and Clarity
<!-- Example: Observability, VI. Versioning & Breaking Changes, VII. Simplicity -->
Content must be accessible to IT professionals with 5-10 years of experience; Language should be clear and jargon-free where possible; Complex concepts must be broken down into digestible sections; Visual aids and diagrams should enhance understanding.
<!-- Example: Text I/O ensures debuggability; Structured logging required; Or: MAJOR.MINOR.BUILD format; Or: Start simple, YAGNI principles -->

### VI. Continuous Updates
Content must be regularly updated to reflect changes in technology, policies, and examination patterns; Mechanisms for incorporating feedback from users and subject matter experts must be established; Version control for content updates is essential.

## Content Standards
<!-- Example: Additional Constraints, Security Requirements, Performance Standards, etc. -->

All content must adhere to the highest academic and professional standards; Chapters must follow a consistent structure and formatting; MCQs must include detailed explanations for both correct and incorrect answers; Appendices should provide supplementary materials and reference resources.
<!-- Example: Technology stack requirements, compliance standards, deployment policies, etc. -->

## Development Workflow
<!-- Example: Development Workflow, Review Process, Quality Gates, etc. -->

Content development follows a structured workflow: Domain identification → Research → Drafting → Expert review → Revision → Quality assurance → Publication; Each phase has specific quality gates and approval requirements; Peer reviews are mandatory for all content; Subject matter experts must validate technical accuracy.
<!-- Example: Code review requirements, testing gates, deployment approval process, etc. -->

## Governance
<!-- Example: Constitution supersedes all other practices; Amendments require documentation, approval, migration plan -->

This constitution governs all aspects of the ADIT preparation book development; All contributors must comply with these principles; Amendments to this constitution require documentation and approval from the editorial board; All PRs/reviews must verify compliance with these principles; Complexity must be justified with clear educational value.

**Version**: 1.0.0 | **Ratified**: 2026-02-01 | **Last Amended**: 2026-02-01
<!-- Example: Version: 2.1.1 | Ratified: 2025-06-13 | Last Amended: 2025-07-16 -->