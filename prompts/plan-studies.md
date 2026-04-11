---
type: prompt
id: plan-studies
title: Plan Studies
description: "Core prompt for creating revision schedules"
tags: [Production, Learning, Academic]
inputs:
  module_name:
    label: "Module Name"
    description: "The name of the course module or subject"
    example: "Introduction to Macroeconomics"
    required: true
    type: text
  exam_date:
    label: "Exam Date"
    description: "When the exam takes place"
    example: "2026-06-15"
    required: true
    type: text
  syllabus_topics:
    label: "Syllabus Topics"
    description: "The list of topics covered in the syllabus"
    example: "Cell biology, genetics, evolution, ecology, human physiology"
    required: true
    type: text
connections:
  - target: study-planning
    type: derived_from
---

## Purpose

Creates a structured revision timetable based on exam dates, syllabus, and self-assessed confidence levels.

## Prompt

You are a study skills advisor. Create a detailed revision timetable for the following exam.

**Module:** {{input.module_name}}
**Exam date:** {{input.exam_date}}
**Syllabus topics and confidence levels:** {{input.syllabus_topics}}
**Syllabus review:** {{steps.previous.output}}

Given the syllabus review above, the exam schedule, syllabus topics, and the student's self-assessed confidence per topic (1-5), create a detailed revision timetable. Allocate more time to low-confidence topics, include regular review sessions for spaced repetition, and build in rest periods. Ensure all topics are covered before the exam date.
