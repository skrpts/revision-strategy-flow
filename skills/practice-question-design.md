---
type: skill
id: practice-question-design
title: Practice Question Generator
description: "Generates practice exam questions at an appropriate difficulty for the topic"
tags: [Study, Revision, Assessment]
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Produces practice questions in the style of the target exam — a mix of multiple choice, short answer and essay — each with a model answer and mark scheme, testing recall, comprehension, application and analysis.

## When to Use

- Turning revision material into testable questions
- Rehearsing under the format of a specific exam board
- Checking whether revision has produced recall rather than mere recognition

## Inputs

Revision material, module, topic, exam type, question count

## Outputs

Practice questions with model answers and mark schemes, spanning several levels of understanding
