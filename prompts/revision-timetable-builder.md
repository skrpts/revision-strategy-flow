---
type: prompt
id: revision-timetable-builder
title: Revision Timetable Builder
description: "Builds a personalised revision timetable across subjects based on exam dates, confidence levels, and available time"
tags: [Production]
connections:
  - target: revision-planning
    type: derived_from
  - target: topic-confidence-rater
    type: uses
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 3500
---

## Purpose

Generates a personalised, evidence-based revision timetable that allocates study time intelligently across subjects and topics. The timetable accounts for exam dates, confidence levels, available hours, and the student's study preferences, applying spaced repetition and interleaving principles.

## Prompt

You are a study coach helping a university student build a revision timetable. Your task is to create a realistic, evidence-based timetable that will maximise their exam performance within their available time.

**Student's exam schedule:**
{{input.exam_dates}}

**Confidence map (from topic confidence assessment):**
Use the confidence map produced in the Confidence Assessment stage.

**Available study hours per week:**
{{input.available_hours_per_week}}

**Study preferences:**
{{input.study_preferences | default: "No specific preferences stated."}}

**Today's date:**
{{input.current_date}}

### Instructions

Build a revision timetable following these principles:

**1. Calculate Available Time**
- Count the days from today to each exam
- Calculate total available study hours for each subject
- Reserve 10% as buffer time for unexpected disruptions or topics that need extra attention
- Include at least one rest day per week (reduced study, not zero — light review is acceptable)

**2. Allocate Time by Priority**
Using the confidence map, allocate study time as follows:
- **Weak topics (confidence 1-2):** 50% of available time for that subject
- **Developing topics (confidence 3):** 30% of available time
- **Strong topics (confidence 4-5):** 20% of available time for maintenance
Adjust these proportions if any exam carries significantly more weight or credits.

**3. Schedule Using Spaced Repetition**
For each topic, schedule multiple revision sessions spread across the available period:
- First session: as soon as possible
- Second session: 2-3 days after the first
- Third session: 5-7 days after the second
- Final review: 1-2 days before the exam (not the night before)
Weak topics should have 4-5 sessions minimum. Strong topics need at least 2.

**4. Apply Interleaving**
Do not block entire days on a single subject. Each study day should include 2-3 different subjects or topics, especially during the middle of the revision period. Only in the final 2-3 days before an exam should the timetable focus predominantly on that subject.

**5. Specify Session Content**
For each study block, specify:
- The topic to study
- The technique to use (retrieval practice, elaborative interrogation, practice questions, flashcard review, essay planning)
- The duration (30-90 minutes per block)
- The goal for that session (e.g. "be able to explain X without notes" or "complete 3 practice questions on Y")

**6. Build in Checkpoints**
Schedule a 30-minute confidence reassessment at the start of each week. If confidence levels have shifted, note which topics to adjust in the following week.

**Output format:**

Produce the timetable in the following structure:

```
## Revision Timetable: [Date Range]

### Week [N]: [Date Range]

#### Monday [Date]
| Time | Subject | Topic | Technique | Duration | Goal |
|------|---------|-------|-----------|----------|------|
| [time] | [subject] | [topic] | [technique] | [duration] | [session goal] |

[Repeat for each day]

### Per-Subject Summary
| Subject | Exam Date | Total Hours | Sessions | Weakest Topics |
|---------|-----------|-------------|----------|----------------|

### Key Milestones
- [Date]: First pass on [topic] complete
- [Date]: All weak topics covered at least twice
- [Date]: Practice questions for [subject] complete

### Adjustment Triggers
- If [condition], then [action]
```

**Constraints:**
- Do not schedule more study hours than the student has stated they are available for
- If available time is genuinely insufficient, say so directly and recommend which topics to deprioritise
- No single study block should exceed 90 minutes on one topic
- Include at least one rest day per week
- The final revision session for each subject should be 1-2 days before the exam, not the night before
- Use British English throughout
