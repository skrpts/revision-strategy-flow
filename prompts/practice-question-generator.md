---
type: prompt
id: practice-question-generator
title: Practice Question Generator
description: "Task prompt for generating exam-style practice questions"
tags: [Tested]
connections:
  - target: note-taking
    type: derived_from
---

## Purpose

Generates practice questions that mirror exam formats for effective revision.

## Prompt

Generate {{input.question_count}} practice questions in the style of {{input.exam_type}}, based on the structured notes and flashcards below. The module is {{input.module_name}} and the topic is {{input.topic}}. Include a mix of question types: multiple choice, short answer, and essay questions. For each question, provide a model answer and mark scheme. Ensure questions test different levels of understanding: recall, comprehension, application, and analysis.

**Structured notes:** {{steps.take-notes.output}}

**Flashcards:** {{steps.flashcard-creator.output}}
