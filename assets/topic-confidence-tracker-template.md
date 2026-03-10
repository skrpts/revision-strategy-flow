---
type: asset
id: topic-confidence-tracker-template
title: Topic Confidence Tracker Template
description: "Reusable template for tracking confidence levels across exam topics over the revision period"
tags: [Production, Customer-Facing]
connections:
  - target: self-assessment
    type: uses
metadata:
  asset_type: "template"
  format: "markdown"
---

# Topic Confidence Tracker

## Header

| Field | Value |
|-------|-------|
| **Student:** | [Name] |
| **Academic year:** | [Year] |
| **Assessment period:** | [e.g. January exams, Summer exams] |
| **First assessment date:** | [DD/MM/YYYY] |
| **Last assessment date:** | [DD/MM/YYYY] |

---

## Confidence Scale

| Level | Label | Meaning | Exam Readiness |
|-------|-------|---------|---------------|
| 5 | Confident | Could write a detailed exam answer now | Ready |
| 4 | Good | Understand key concepts, might miss nuances | Nearly ready |
| 3 | Developing | Know basics, need revision to answer fully | Needs work |
| 2 | Weak | Vaguely familiar, cannot explain key concepts | Needs significant work |
| 1 | Minimal | Barely engaged with this topic | Urgent attention needed |

**Rating rule:** Rate three dimensions separately (Conceptual, Application, Communication). The overall rating is the **minimum** of the three, not the average.

---

## Module 1: [Module Name]

**Exam date:** [DD/MM/YYYY] | **Exam format:** [Format] | **Weighting:** [%]

### Topic Ratings

| Topic | Conceptual | Application | Communication | Overall | Week 1 | Week 2 | Week 3 | Week 4 | Trend |
|-------|-----------|-------------|---------------|---------|--------|--------|--------|--------|-------|
| [Topic 1] | [1-5] | [1-5] | [1-5] | [min] | [1-5] | [1-5] | [1-5] | [1-5] | [up/down/flat] |
| [Topic 2] | [1-5] | [1-5] | [1-5] | [min] | | | | | |
| [Topic 3] | [1-5] | [1-5] | [1-5] | [min] | | | | | |
| [Topic 4] | [1-5] | [1-5] | [1-5] | [min] | | | | | |
| [Topic 5] | [1-5] | [1-5] | [1-5] | [min] | | | | | |

### Calibration Notes
- **Overconfidence flags:** [Topics rated 4-5 that have not been tested recently]
- **Blind spots:** [Topics missing from the list or not engaged with]
- **Quick wins:** [Topics at 2-3 that could improve rapidly with focused effort]

---

## Module 2: [Module Name]

**Exam date:** [DD/MM/YYYY] | **Exam format:** [Format] | **Weighting:** [%]

### Topic Ratings

| Topic | Conceptual | Application | Communication | Overall | Week 1 | Week 2 | Week 3 | Week 4 | Trend |
|-------|-----------|-------------|---------------|---------|--------|--------|--------|--------|-------|
| [Topic 1] | [1-5] | [1-5] | [1-5] | [min] | [1-5] | [1-5] | [1-5] | [1-5] | [up/down/flat] |
| [Topic 2] | [1-5] | [1-5] | [1-5] | [min] | | | | | |
| [Topic 3] | [1-5] | [1-5] | [1-5] | [min] | | | | | |

### Calibration Notes
- **Overconfidence flags:** [Topics rated 4-5 that have not been tested recently]
- **Blind spots:** [Topics missing from the list or not engaged with]
- **Quick wins:** [Topics at 2-3 that could improve rapidly with focused effort]

---

## Module 3: [Module Name]

[Repeat the same structure for each additional module]

---

## Priority Summary

### Urgent Revision Needed (Overall 1-2)

| Module | Topic | Overall | Exam Date | Sessions Needed |
|--------|-------|---------|-----------|----------------|
| [Module] | [Topic] | [1-2] | [Date] | [4-5 sessions] |

### Focused Revision Needed (Overall 3)

| Module | Topic | Overall | Exam Date | Sessions Needed |
|--------|-------|---------|-----------|----------------|
| [Module] | [Topic] | [3] | [Date] | [2-3 sessions] |

### Maintenance Revision (Overall 4-5)

| Module | Topic | Overall | Exam Date | Sessions Needed |
|--------|-------|---------|-----------|----------------|
| [Module] | [Topic] | [4-5] | [Date] | [1-2 sessions] |

---

## Weekly Reassessment Log

### Week 1: [DD/MM/YYYY]
- **Topics that improved:** [List with old and new ratings]
- **Topics that did not improve:** [List — investigate why]
- **New blind spots identified:** [Any]
- **Timetable adjustments needed:** [Yes/No — what changes]

### Week 2: [DD/MM/YYYY]
[Same format]

### Week 3: [DD/MM/YYYY]
[Same format]

---

## Post-Exam Calibration

After each exam, compare your pre-exam confidence ratings with your actual performance:

| Module | Topic | Pre-Exam Rating | Actual Performance | Calibration |
|--------|-------|-----------------|-------------------|-------------|
| [Module] | [Topic] | [1-5] | [How it went] | [Accurate / Overconfident / Underconfident] |

**Lessons for future assessments:**
- [What to adjust in future self-assessments based on calibration accuracy]

---

## Usage Instructions

1. Fill in the Header and list all modules and topics before starting revision.
2. Complete the initial confidence assessment using the Topic Confidence Rater prompt.
3. Rate each topic on all three dimensions (Conceptual, Application, Communication).
4. Use the Priority Summary to feed into the Revision Timetable Builder.
5. Reassess weekly — update the Week columns and note trends.
6. After exams, complete the Post-Exam Calibration to improve future assessments.
7. Keep this tracker throughout the academic year — your calibration accuracy will improve over time.
