---
type: prompt
id: practice-question-generator
title: Practice Question Generator
description: "Task prompt for generating exam-style practice questions"
tags: [Tested, Learning, Academic]
inputs:
  question_count:
    label: "Question Count"
    description: "Number of questions to generate"
    example: "10"
    required: true
    type: text
  exam_type:
    label: "Exam Type"
    description: "The format of the exam"
    example: "Written essay exam, 3 hours, choose 3 from 6 questions"
    required: true
    type: text
  module_name:
    label: "Module Name"
    description: "The name of the course module or subject"
    example: "Introduction to Macroeconomics"
    required: true
    type: text
  topic:
    label: "Topic"
    description: "The main subject or topic to address"
    example: "The impact of remote work on team productivity"
    required: true
    type: text
connections:
  - target: note-taking
    type: derived_from
---

## Purpose

Generates practice questions that mirror exam formats for effective revision.

## Prompt

Generate {{input.question_count}} practice questions in the style of {{input.exam_type}}, based on the structured notes and flashcards below. The module is {{input.module_name}} and the topic is {{input.topic}}. Include a mix of question types: multiple choice, short answer, and essay questions. For each question, provide a model answer and mark scheme. Ensure questions test different levels of understanding: recall, comprehension, application, and analysis.

**Structured notes:** {{steps.Take Notes.output}}

**Flashcards:** {{steps.Flashcard Creator.output}}
