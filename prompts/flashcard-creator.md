---
type: prompt
id: flashcard-creator
title: Flashcard Creator
description: "Simple study flashcard generator — creates question-and-answer cards from structured notes for active recall practice"
tags: [Production, Learning, Academic]
connections:
  - target: note-taking
    type: derived_from
---

## Purpose

Creates flashcards from study notes for active recall practice.

## Prompt

Create {{input.card_count}} flashcards from the structured notes below. The module is {{input.module_name}} and the topic is {{input.topic}}. Each flashcard should have a clear question on the front and a concise answer on the back. Include a mix of: definition cards, concept explanation cards, and application cards. Order them from fundamental concepts to more advanced topics.

**Structured notes:** {{steps.Take Notes.output}}

Format each card as:

**Front:** [question]
**Back:** [answer]
