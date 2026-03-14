---
type: skill
id: revision-planning
title: Revision Planning
description: "Designs personalised revision timetables that allocate study time based on exam dates, topic difficulty, confidence levels, and available hours"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: learning-science-reference
    type: references
  - target: revision-strategy-guide
    type: references
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 3000
---

## Capability

Revision Planning takes a student's exam schedule, confidence map, and available time, then produces a structured revision timetable that maximises learning outcomes within the constraints. It applies evidence-based scheduling principles: spaced repetition intervals, interleaving of subjects, prioritisation of weak areas, and built-in review sessions.

This skill understands that revision is not about spending equal time on every topic. It weights allocation towards topics where the student is least confident, while ensuring strong topics receive maintenance sessions to prevent decay. It also accounts for the psychological reality of revision — scheduling easier topics at low-energy times and harder topics at peak focus periods.

## Planning Approach

### Input Analysis
1. Parse the student's exam dates and calculate the available revision days for each subject
2. Analyse the confidence map to identify topics requiring heavy, moderate, or light revision
3. Account for the student's stated available hours per day and any commitments or rest days
4. Identify dependencies between topics (where understanding Topic A is prerequisite for Topic B)

### Scheduling Principles
1. **Spaced repetition:** Schedule each topic for multiple sessions spread across the revision period, with increasing intervals between sessions. A topic first studied on Monday should be revisited Wednesday, then the following Monday, then ten days later.
2. **Interleaving:** Mix subjects and topics within each study day rather than blocking entire days on one subject. Research shows interleaving improves discrimination and long-term retention.
3. **Priority weighting:** Allocate approximately 50% of time to weak topics, 30% to developing topics, and 20% to maintenance of strong topics. Adjust based on exam weighting if provided.
4. **Diminishing returns:** No single topic should receive more than 90 minutes of continuous study. After that, switch to a different subject or take a break.
5. **Review sessions:** Schedule dedicated review sessions (30 minutes) at the start of each week to reassess confidence and adjust the timetable.
6. **Buffer time:** Reserve 10-15% of available time as buffer for topics that prove harder than expected or for unexpected disruptions.

### Output Structure
1. Weekly view showing each day's study blocks with specific topics and techniques
2. Per-subject summary showing total hours allocated and session distribution
3. Key milestones (when each topic should have its first pass, second pass, and final review)
4. Adjustment triggers (conditions that should prompt a timetable revision)

## Quality Criteria

- The timetable must be realistic given the stated available hours — do not schedule 12-hour days
- Every examined topic must appear at least twice in the timetable
- Weak topics must appear at least three times, with the final session no more than 3 days before the exam
- No study block should exceed 90 minutes on a single topic
- Rest days or reduced-load days must be included (at least one per week)
- The timetable should specify what to do in each session, not just which topic to study

## Constraints

- Do not assume the student has unlimited time or motivation
- If the available time is genuinely insufficient to cover all topics adequately, say so explicitly and help the student make strategic choices about what to prioritise
- Do not frontload all difficult topics at the start — this leads to burnout and abandonment
- Account for exam dates: the final revision session for each subject should be 1-2 days before its exam, not the night before
