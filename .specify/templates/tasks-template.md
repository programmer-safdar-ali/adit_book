---

description: "Task list template for feature implementation"
---

# Tasks: [FEATURE NAME]

**Input**: Design documents from `/specs/[###-feature-name]/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: The examples below include test tasks. Tests are OPTIONAL - only include them if explicitly requested in the feature specification.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Single project**: `src/`, `tests/` at repository root
- **Web app**: `backend/src/`, `frontend/src/`
- **Mobile**: `api/src/`, `ios/src/` or `android/src/`
- Paths shown below assume single project - adjust based on plan.md structure

<!-- 
  ============================================================================
  IMPORTANT: The tasks below are SAMPLE TASKS for illustration purposes only.
  
  The /sp.tasks command MUST replace these with actual tasks based on:
  - User stories from spec.md (with their priorities P1, P2, P3...)
  - Feature requirements from plan.md
  - Entities from data-model.md
  - Endpoints from contracts/
  
  Tasks MUST be organized by user story so each story can be:
  - Implemented independently
  - Tested independently
  - Delivered as an MVP increment
  
  DO NOT keep these sample tasks in the generated tasks.md file.
  ============================================================================
-->

## Phase 1: Content Framework (Shared Structure)

**Purpose**: Establish the foundational structure for the ADIT preparation book

- [ ] T001 Create project structure for 25 knowledge domains
- [ ] T002 Develop template for domain chapters with consistent formatting
- [ ] T003 [P] Configure content management tools and version control

---

## Phase 2: Foundational Content (Blocking Prerequisites)

**Purpose**: Core content elements that MUST be complete before ANY domain can be developed

**⚠️ CRITICAL**: No domain work can begin until this phase is complete

Examples of foundational tasks (adjust based on your project):

- [ ] T004 Establish content standards and style guide for all domains
- [ ] T005 [P] Define assessment framework for MCQs and practice tests
- [ ] T006 [P] Create template for practical application scenarios
- [ ] T007 Develop index and cross-reference system for all domains
- [ ] T008 Configure quality assurance and review processes
- [ ] T009 Setup content management and version control system

**Checkpoint**: Foundation ready - domain implementation can now begin in parallel

---

## Phase 3: Domain 1 - [Domain Title] (Priority: P1) 🎯 Core Foundation

**Goal**: [Brief description of what this domain delivers]

**Independent Test**: [How to verify this domain works on its own]

### Content Review for Domain 1 (OPTIONAL - only if reviews requested) ⚠️

> **NOTE: Reviews should be conducted FIRST, ensure content meets standards before finalizing**

- [ ] T010 [P] [D1] Content review for [domain topic] in domains/[domain-name]/content.md
- [ ] T011 [P] [D1] MCQ validation for [domain topic] in domains/[domain-name]/assessments.md

### Implementation for Domain 1

- [ ] T012 [P] [D1] Research and outline [Topic 1] in domains/[domain-name]/topics/[topic1].md
- [ ] T013 [P] [D1] Research and outline [Topic 2] in domains/[domain-name]/topics/[topic2].md
- [ ] T014 [D1] Write comprehensive content for [Topic 1] in domains/[domain-name]/topics/[topic1].md (depends on T012)
- [ ] T015 [D1] Write comprehensive content for [Topic 2] in domains/[domain-name]/topics/[topic2].md (depends on T013)
- [ ] T016 [D1] Add practical application examples and scenarios
- [ ] T017 [D1] Compile 200+ MCQs with detailed explanations for this domain

**Checkpoint**: At this point, Domain 1 should be fully developed and reviewable independently

---

## Phase 4: Domain 2 - [Domain Title] (Priority: P2)

**Goal**: [Brief description of what this domain delivers]

**Independent Test**: [How to verify this domain works on its own]

### Content Review for Domain 2 (OPTIONAL - only if reviews requested) ⚠️

- [ ] T018 [P] [D2] Content review for [domain topic] in domains/[domain-name]/content.md
- [ ] T019 [P] [D2] MCQ validation for [domain topic] in domains/[domain-name]/assessments.md

### Implementation for Domain 2

- [ ] T020 [P] [D2] Research and outline [Topic] in domains/[domain-name]/topics/[topic].md
- [ ] T021 [D2] Write comprehensive content for [domain topic] in domains/[domain-name]/content.md
- [ ] T022 [D2] Add practical application examples and scenarios
- [ ] T023 [D2] Integrate with Domain 1 concepts (if cross-domain connections exist)

**Checkpoint**: At this point, Domains 1 AND 2 should both work independently

---

## Phase 5: Domain 3 - [Domain Title] (Priority: P3)

**Goal**: [Brief description of what this domain delivers]

**Independent Test**: [How to verify this domain works on its own]

### Content Review for Domain 3 (OPTIONAL - only if reviews requested) ⚠️

- [ ] T024 [P] [D3] Content review for [domain topic] in domains/[domain-name]/content.md
- [ ] T025 [P] [D3] MCQ validation for [domain topic] in domains/[domain-name]/assessments.md

### Implementation for Domain 3

- [ ] T026 [P] [D3] Research and outline [Topic] in domains/[domain-name]/topics/[topic].md
- [ ] T027 [D3] Write comprehensive content for [domain topic] in domains/[domain-name]/content.md
- [ ] T028 [D3] Add practical application examples and scenarios

**Checkpoint**: All domains should now be independently functional

---

[Add more user story phases as needed, following the same pattern]

---

## Phase N: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [ ] TXXX [P] Documentation updates in docs/
- [ ] TXXX Code cleanup and refactoring
- [ ] TXXX Performance optimization across all stories
- [ ] TXXX [P] Additional unit tests (if requested) in tests/unit/
- [ ] TXXX Security hardening
- [ ] TXXX Run quickstart.md validation

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Stories (Phase 3+)**: All depend on Foundational phase completion
  - User stories can then proceed in parallel (if staffed)
  - Or sequentially in priority order (P1 → P2 → P3)
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### Domain Dependencies

- **Domain 1 (P1)**: Can start after Foundational (Phase 2) - No dependencies on other domains
- **Domain 2 (P2)**: Can start after Foundational (Phase 2) - May connect with D1 but should be independently reviewable
- **Domain 3 (P3)**: Can start after Foundational (Phase 2) - May connect with D1/D2 but should be independently reviewable

### Within Each Domain

- Content research before writing
- Topic outlines before comprehensive content
- Content before assessments
- Core concepts before practical applications
- Domain complete before moving to next priority

### Parallel Opportunities

- All Setup tasks marked [P] can run in parallel
- All Foundational tasks marked [P] can run in parallel (within Phase 2)
- Once Foundational phase completes, all user stories can start in parallel (if team capacity allows)
- All tests for a user story marked [P] can run in parallel
- Models within a story marked [P] can run in parallel
- Different user stories can be worked on in parallel by different team members

---

## Parallel Example: Domain 1

```bash
# Launch all content reviews for Domain 1 together (if reviews requested):
Task: "Content review for [domain topic] in domains/[domain-name]/content.md"
Task: "MCQ validation for [domain topic] in domains/[domain-name]/assessments.md"

# Launch all topics for Domain 1 together:
Task: "Research and outline [Topic 1] in domains/[domain-name]/topics/[topic1].md"
Task: "Research and outline [Topic 2] in domains/[domain-name]/topics/[topic2].md"
```

---

## Implementation Strategy

### Core Foundation First (Domain 1 Only)

1. Complete Phase 1: Content Framework
2. Complete Phase 2: Foundational Content (CRITICAL - blocks all domains)
3. Complete Phase 3: Domain 1
4. **STOP and REVIEW**: Validate Domain 1 independently
5. Review/demo if ready

### Incremental Delivery

1. Complete Framework + Foundational → Foundation ready
2. Add Domain 1 → Review independently → Review/Demo (Core!)
3. Add Domain 2 → Review independently → Review/Demo
4. Add Domain 3 → Review independently → Review/Demo
5. Each domain adds value without affecting previous domains

### Parallel Team Strategy

With multiple content developers:

1. Team completes Framework + Foundational together
2. Once Foundational is done:
   - Developer A: Domain 1
   - Developer B: Domain 2
   - Developer C: Domain 3
3. Domains complete and integrate independently

---

## Notes

- [P] tasks = different files, no dependencies
- [D#] label maps task to specific domain for traceability
- Each domain should be independently developable and reviewable
- Verify content meets quality standards before finalizing
- Commit after each task or logical group
- Stop at any checkpoint to validate domain independently
- Avoid: vague tasks, same file conflicts, cross-domain dependencies that break independence
