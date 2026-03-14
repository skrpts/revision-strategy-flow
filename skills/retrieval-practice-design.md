---
type: skill
id: retrieval-practice-design
title: Retrieval Practice Design
description: "Designs revision sessions and practice questions using retrieval practice, elaborative interrogation, interleaving, and other evidence-based learning techniques"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: learning-science-reference
    type: references
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 3000
---

## Capability

Retrieval Practice Design creates structured revision sessions and practice questions that leverage the testing effect — the finding that actively retrieving information from memory strengthens long-term retention far more effectively than passive review. It combines multiple evidence-based techniques into coherent session plans that students can follow independently.

This skill understands that different topics and different confidence levels require different approaches. A student who is weak on a topic needs more scaffolded retrieval with immediate feedback. A student who is strong needs challenging application questions and interleaved practice to maintain and deepen their understanding.

## Session Design Principles

### The Testing Effect
The core principle: attempting to retrieve information from memory — even unsuccessfully — strengthens the memory trace more than re-reading or re-studying. Every revision session should include retrieval attempts, not just review.

### Elaborative Interrogation
Asking "why" and "how" questions about material forces deeper processing than simple recall. For each key concept in a revision session, generate "why is this true?" and "how does this connect to X?" questions.

### Interleaving
Mixing different topics or problem types within a single session improves the student's ability to discriminate between concepts and select the right approach. Sessions should not be blocked by topic — they should interleave related (but distinct) concepts.

### Self-Explanation
Prompting students to explain their reasoning as they work through problems or answer questions. This surfaces misconceptions and strengthens understanding.

### Successive Relearning
Combining retrieval practice with spaced repetition. Topics are tested, then restudied only where retrieval failed, then tested again at increasing intervals.

## Session Structure

### For Weak Topics (Confidence 1-2)
1. **Orientation (5 min):** Brief review of the key concepts — just enough to prime retrieval
2. **Guided retrieval (15 min):** Answer questions with hints available; check answers immediately
3. **Self-explanation (10 min):** Explain the key concepts aloud or in writing without notes
4. **Gap identification (5 min):** Note what could not be retrieved or explained
5. **Targeted restudy (10 min):** Review only the gaps identified
6. **Final retrieval (5 min):** Attempt the same questions again without hints

### For Developing Topics (Confidence 3)
1. **Free recall (10 min):** Write everything known about the topic from memory
2. **Check and correct (5 min):** Compare against notes, mark gaps
3. **Elaborative interrogation (10 min):** Answer "why" and "how" questions about key concepts
4. **Interleaved practice (15 min):** Mix questions from this topic with questions from a related topic
5. **Self-assessment (5 min):** Rate understanding after the session

### For Strong Topics (Confidence 4-5)
1. **Application challenge (15 min):** Novel scenario or essay plan that requires applying the concepts
2. **Interleaved retrieval (15 min):** Mix questions from this topic with questions from 2-3 other topics
3. **Teaching test (10 min):** Explain the topic as if teaching someone who knows nothing about it
4. **Edge cases (5 min):** Identify and address exceptions, limitations, or nuances

## Practice Question Design

### Question Types by Difficulty
- **Beginner:** Define, list, identify — test recall of foundational knowledge
- **Intermediate:** Explain, compare, distinguish — test comprehension and analysis
- **Advanced:** Apply, evaluate, synthesise — test transfer and critical thinking

### Question Calibration
Questions should be slightly harder than the student's current level — the "desirable difficulty" principle. If the student answers correctly with ease, the question is too easy. If they cannot even begin to answer, it is too hard. The sweet spot is where retrieval requires effort but is achievable.

### Model Answers
Every practice question must include a model answer that:
- Demonstrates the expected level of detail and structure
- Highlights the key points that would earn marks
- Notes common misconceptions or errors to avoid
- Indicates approximately how much time the answer should take under exam conditions

## Quality Criteria

- Every session must include at least one retrieval attempt without notes
- Sessions for weak topics must include immediate feedback — do not let errors persist
- Practice questions must match the stated difficulty level
- Model answers must be genuinely useful, not just restated questions
- The session plan must include specific timings that add up to the stated session duration
- Techniques must be appropriate to the topic type (e.g. do not use interleaving for a topic the student has never studied)

## Constraints

- Do not create sessions longer than 60 minutes — attention and retention decline sharply after this point
- Do not assume the student has access to specific resources unless stated
- If the exam format is known, align practice questions to that format
- Never generate questions that test content outside what the student has provided
- Do not confuse difficulty with obscurity — a hard question tests deep understanding, not trivia
