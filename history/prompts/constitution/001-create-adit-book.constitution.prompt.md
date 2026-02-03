---
id: "001"
title: "Create ADIT Book Constitution"
stage: "constitution"
date_iso: "2026-02-01"
surface: "agent"
model: "Qwen Code"
feature: "none"
branch: "main"
user: "safdaralishah"
command: "/sp.constitution"
labels:
  - "constitution"
  - "adit"
  - "book"
links:
  spec: null
  ticket: null
  adr: null
  pr: null
files_yaml:
  - ".specify/memory/constitution.md"
  - ".specify/templates/plan-template.md"
  - ".specify/templates/spec-template.md"
  - ".specify/templates/tasks-template.md"
tests_yaml: []
prompt_text: |
  /sp.constitution Create a Project Constitution for a comprehensive preparation book for the post of Assistant Director IT. The book should cover all 25 knowledge domains from the approved study plan, include 5000+ MCQs, and prepare candidates for both competitive exams and the actual job role.
  Key Elements to Define:

  Project vision and mission
  Scope (25 domains, 1000+ pages, 5000+ MCQs)
  Target audience (IT professionals with 5-10 years experience)
  Deliverables (chapters, assessments, appendices)
  Quality standards (accuracy, consistency, readability)
  Success criteria and metrics
  Risks and mitigation
  Timeline and milestones
  Constraints and assumptions

  Alignment: Base it on the job profile of Assistant Director IT covering Infrastructure Management, Security & Policy, Project Coordination, Technical Support, and Administrative Tasks.
  Output: A formal, structured constitution document that serves as the governing framework for the entire book project.
response_text: |
  Created a comprehensive Project Constitution for the Assistant Director IT preparation book project. The constitution includes six core principles:
  
  1. Comprehensive Coverage - ensuring all 25 knowledge domains are thoroughly covered
  2. Quality Assurance - rigorous quality checks and expert reviews
  3. Exam-Focused Approach - content structured for both competitive exams and job responsibilities
  4. Practical Application Focus - linking theory to real-world scenarios
  5. Accessibility and Clarity - content accessible to IT professionals with 5-10 years experience
  6. Continuous Updates - mechanisms for incorporating feedback and updates
  
  Also updated dependent templates to align with the ADIT book project:
  - Modified plan-template.md to include constitution checks specific to the ADIT project
  - Updated spec-template.md with functional requirements for the ADIT book
  - Revised tasks-template.md to reflect domain-focused development instead of user stories
outcome: |
  Successfully created a comprehensive constitution for the ADIT preparation book project and updated all dependent templates to align with the project's unique requirements.
evaluation: |
  The constitution clearly defines the project's principles, standards, and governance structure. All dependent templates have been updated to reflect the ADIT book project's focus on knowledge domains rather than traditional software features.
---