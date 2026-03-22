---
type: skill
id: self-assessment
title: Self-Assessment
description: "Guides students through honest evaluation of their understanding across topics, identifying genuine confidence levels and blind spots"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: learning-science-reference
    type: references
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 2500
---

## Capability

Self-Assessment helps students evaluate their understanding of exam topics honestly and systematically. It combats the Dunning-Kruger effect and the illusion of fluency — where re-reading notes creates false confidence — by using structured evaluation criteria rather than gut feeling.

This skill produces confidence maps that drive the rest of the revision pipeline. If the assessment is inaccurate, the entire revision strategy will be misallocated. Therefore, this skill includes calibration techniques that challenge students to test their understanding before rating it.

## Assessment Approach

### Pre-Assessment Calibration
Before asking students to rate their confidence, challenge them with quick diagnostic checks:
1. **Explain it simply:** Can the student explain the topic in plain language to someone outside the subject? If not, their understanding is likely shallower than they think.
2. **Predict the exam question:** Can the student predict what kind of exam question might be asked on this topic? Inability to do so suggests a surface-level understanding.
3. **Identify the gaps:** Can the student identify what they do NOT know about the topic? Students who say "I know everything" about a topic almost certainly have blind spots.

### Confidence Rating Scale
Rate each topic on a 5-point scale with behavioural anchors:

| Level | Label | Behavioural Anchor |
|-------|-------|-------------------|
| 5 | Confident | Could write a clear, detailed essay answer under exam conditions right now |
| 4 | Good | Understand the key concepts and can explain them, but might miss nuances or edge cases |
| 3 | Developing | Know the basics but could not answer an exam question fully without further revision |
| 2 | Weak | Recognise the topic but could not explain the key concepts coherently |
| 1 | Minimal | Have barely engaged with this topic — would struggle to say anything meaningful about it |

### Assessment Dimensions
For each topic, assess three dimensions separately:
1. **Conceptual understanding:** Do you understand the key ideas and theories?
2. **Application ability:** Can you apply these concepts to new scenarios or examples?
3. **Communication readiness:** Can you write or speak about this topic coherently under time pressure?

The overall confidence rating is the minimum of these three dimensions, not the average. A student who understands a concept but cannot articulate it under exam conditions is not exam-ready.

### Blind Spot Detection
After the student completes their self-assessment:
1. Look for topics rated 4 or 5 that have not been recently tested — these may be overconfident ratings
2. Look for entire modules or themes that are missing from the assessment — these are genuine blind spots
3. Compare current ratings against any past exam results provided — significant discrepancies warrant investigation

## Quality Criteria

- Ratings must be justified with specific evidence, not just feelings
- The assessment must cover every topic that will be examined
- Blind spots must be explicitly identified and flagged
- The output must prioritise topics clearly: which need urgent attention, which need maintenance, which are secure
- Reassessment after revision sessions should show movement — if ratings never change, the student may not be engaging honestly

## Constraints

- Do not inflate ratings to make the student feel better — honest assessment is the foundation of effective revision
- Do not assess topics the student has not listed — work with what they provide, but flag if coverage seems incomplete
- If past exam results are provided, use them as a reality check but do not assume past performance perfectly predicts future performance
- The goal is actionable prioritisation, not a thorough diagnostic — keep the output focused
