---
type: workflow
id: revision-strategy-flow
title: Revision Strategy Flow
description: "End-to-end workflow for building and executing personalised revision strategies using evidence-based learning techniques"
tags: [Production, Tested]
connections:
  - target: revision-planning
    type: uses
  - target: self-assessment
    type: uses
  - target: retrieval-practice-design
    type: uses
  - target: revision-timetable-builder
    type: uses
  - target: topic-confidence-rater
    type: uses
  - target: practice-question-generator
    type: uses
  - target: active-recall-session-designer
    type: uses
  - target: post-exam-reflector
    type: uses
  - target: claude-service
    type: runs_on
  - target: learning-science-reference
    type: references
  - target: revision-strategy-guide
    type: references
  - target: revision-timetable-template
    type: uses
  - target: topic-confidence-tracker-template
    type: uses
metadata:
  estimated_duration: "30-60 minutes for initial setup, then ongoing"
  trigger: manual
---

## Overview

The Revision Strategy Flow guides students from initial revision planning through to post-exam reflection. It begins by assessing what needs revising and how confident the student feels across their topics, then builds a personalised timetable, designs focused revision sessions using evidence-based techniques, generates practice questions, and finally reflects on exam performance to improve future strategy. The flow is designed to run iteratively — the confidence assessment and timetable are updated regularly as revision progresses.

## Pipeline Stages

### Stage 1: Confidence Assessment

**Trigger:** Start of revision period, or weekly during revision.

Invoke the **topic-confidence-rater** prompt using the **self-assessment** skill. The student provides their list of modules, topics within each module, and their honest assessment of how well they understand each one. The output is a structured confidence map that identifies strong areas, weak areas, and blind spots.

**Input:** Module and topic list via `{{modules_and_topics}}`, plus any past exam results via `{{past_results}}`
**Output:** Confidence map with topics rated and prioritised, using the topic-confidence-tracker-template
**Error handling:** If the student cannot list their topics, suggest they consult their module handbook or course specification first. If confidence ratings are all "high," challenge the student to test themselves before accepting those ratings.

### Stage 2: Timetable Construction

**Trigger:** After Stage 1 completes, or when exam dates change.

Invoke the **revision-timetable-builder** prompt using the **revision-planning** skill. Takes the confidence map from Stage 1, the student's exam dates, and their available study time, then produces a personalised revision timetable that prioritises weak areas while maintaining coverage of strong ones.

**Input:** Confidence map via `{{confidence_map}}`, exam dates via `{{exam_dates}}`, available hours via `{{available_hours_per_week}}`, study preferences via `{{study_preferences}}`
**Output:** Revision timetable using the revision-timetable-template
**Error handling:** If exam dates are less than one week away, switch to a compressed revision plan that focuses exclusively on high-impact topics. If available time is unrealistically low, flag this honestly and help the student prioritise ruthlessly.

### Stage 3: Active Revision Sessions

**Trigger:** Each study session according to the timetable.

Invoke the **active-recall-session-designer** prompt using the **retrieval-practice-design** skill. Designs a focused revision session for a specific topic using evidence-based techniques: retrieval practice, elaborative interrogation, interleaving, and self-explanation. Each session has a clear structure, timing, and success criteria.

**Input:** Topic to revise via `{{topic}}`, session duration via `{{session_duration}}`, available materials via `{{available_materials}}`, current confidence level via `{{confidence_level}}`
**Output:** Structured revision session plan with activities, timings, and self-check criteria
**Error handling:** If the student reports the session was too easy, increase difficulty for next time. If too hard, break the topic into smaller sub-topics and tackle them sequentially.

### Stage 4: Practice Questions

**Trigger:** After completing 2-3 revision sessions on a topic, or on demand.

Invoke the **practice-question-generator** prompt using the **retrieval-practice-design** skill. Generates practice exam questions at the appropriate difficulty level for the topic, including both short-answer and essay-style questions where relevant. Questions are modelled on real exam formats where the student has provided past paper examples.

**Input:** Topic via `{{topic}}`, exam format via `{{exam_format}}`, difficulty level via `{{difficulty}}`, number of questions via `{{question_count}}`, past paper examples via `{{past_paper_examples}}`
**Output:** Set of practice questions with model answers and marking guidance
**Error handling:** If the student has not provided exam format information, generate a mix of question types and recommend they check their module's past papers for format guidance.

### Stage 5: Post-Exam Reflection

**Trigger:** After each exam or mock exam.

Invoke the **post-exam-reflector** prompt using the **self-assessment** skill. Guides the student through a structured reflection on their exam performance — what went well, what did not, how effective their revision strategy was, and what to change for next time.

**Input:** Exam details via `{{exam_details}}`, preparation approach via `{{revision_approach}}`, self-assessed performance via `{{performance_assessment}}`, specific difficulties via `{{difficulties_encountered}}`
**Output:** Structured reflection with actionable improvements for future revision
**Error handling:** If the student is distressed about their performance, acknowledge this and focus the reflection on constructive, forward-looking actions rather than dwelling on mistakes.

## Iterative Loop

Stages 1-4 form an iterative loop during the revision period:
1. Assess confidence (Stage 1) — update weekly
2. Adjust timetable (Stage 2) — update as confidence changes
3. Execute sessions (Stage 3) — daily during revision
4. Test with practice questions (Stage 4) — after every 2-3 sessions per topic

Stage 5 runs after exams and feeds back into Stage 1 for the next exam period.

## Completion Criteria

The flow is considered complete for an exam period when:
1. All topics have been assessed for confidence
2. A timetable covering all exams has been built and followed
3. Each weak topic has had at least 3 focused revision sessions
4. Practice questions have been attempted for every examined topic
5. Post-exam reflections have been completed and filed for future reference
