---
type: service
id: claude-service
title: Claude Service
description: "Anthropic Claude API configuration for revision planning, self-assessment, practice question generation, and session design tasks"
tags: [Production, Tested]
connections:
  - target: anthropic-claude
    type: depends_on
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
---

## Service Configuration

This skrpt uses Anthropic Claude as its AI backbone for all revision planning, confidence assessment, practice question generation, and session design tasks. Claude's instruction-following precision and ability to maintain consistent assessment frameworks make it well-suited to educational coaching tasks where accuracy and honesty matter more than creativity.

## How This Skrpt Uses Claude

### Confidence Assessment (Stage 1)
- **Task:** Guide students through structured self-assessment with calibration challenges
- **Context requirements:** Moderate (1,000-5,000 tokens of module/topic information)
- **Temperature:** Low (0.2) for consistent, honest assessment without inflation
- **Output length:** 500-1,500 tokens depending on number of topics

### Timetable Construction (Stage 2)
- **Task:** Generate personalised revision timetables with spaced repetition scheduling
- **Context requirements:** High (3,000-10,000 tokens including confidence map, exam dates, and preferences)
- **Temperature:** Low (0.2-0.3) for precise scheduling with realistic time allocations
- **Output length:** 1,500-4,000 tokens for multi-week timetables

### Session Design (Stage 3)
- **Task:** Design structured revision sessions with retrieval practice activities
- **Context requirements:** Moderate (2,000-5,000 tokens of topic content and confidence data)
- **Temperature:** Moderate (0.4) to generate varied retrieval questions and scenarios
- **Output length:** 800-1,500 tokens per session plan

### Practice Question Generation (Stage 4)
- **Task:** Generate exam-style questions with model answers and marking guidance
- **Context requirements:** Moderate-High (3,000-8,000 tokens of topic content and past paper examples)
- **Temperature:** Moderate (0.4-0.5) for varied question styles while maintaining accuracy
- **Output length:** 500-800 tokens per question including model answer

### Post-Exam Reflection (Stage 5)
- **Task:** Guide structured reflection and produce improvement plans
- **Context requirements:** Moderate (2,000-5,000 tokens of exam details and self-assessment)
- **Temperature:** Low-moderate (0.3) for honest, constructive feedback
- **Output length:** 1,000-2,000 tokens

## Authentication

Requires an Anthropic API key configured in the Skrptiq app's service settings. No additional permissions or network access required beyond the Anthropic API endpoint.
