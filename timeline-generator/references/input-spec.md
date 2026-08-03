# Input Spec

Default input is a client brief and/or proposal plus natural-language instructions. Do not require users to prepare a structured input sheet.

In normal use, the proposal already has a rough timeline. Treat it as the primary timing source and refine it rather than replacing it.

## Normal Starting Materials

Before a timeline exists, expect one of:

- client brief only.
- proposal only.
- both brief and proposal.

Treat screeners, guides, sample tables, and meeting notes as optional later materials, not required inputs.

When both brief and proposal exist, use the proposal for committed project approach, deliverables, and rough timing; use the brief to understand client background and business constraints.

## What to Extract From Brief / Proposal

Extract the following if present:

- project name, client name, and client short name.
- background, project purpose, business question, and research question.
- research methods, such as desk research, social listening, digital diary, IDI, FGD, ethnography, KOL interview, expert interview, or survey.
- sample and recruitment scale, such as city count, group count, respondent count, segment definitions, and recruitment criteria.
- major deliverables, such as research design, screener, recruitment table, guide, fieldwork schedule, Topline, PPT report, final report, presentation, or archive.
- big time: kickoff, fieldwork window, topline deadline, report delivery, final presentation, or client business deadline.
- rough proposal timeline: phase windows, milestone dates, delivery sequence, and any stated assumptions.
- client collaboration needs, such as feedback rounds, document review, interview observation, sample approval, KOL invitation, progress dashboard access, or leadership reporting.
- known holidays, blackout dates, client review windows, and business deadlines.

## What to Ask the User

Ask only for information that materially affects the schedule. Do not ask for all missing fields.

Highest-priority follow-up questions:

- kickoff / start date.
- final report or final presentation date.
- fixed intermediate milestones.
- client involvement intensity.
- holidays, client review windows, or immovable business dates.

Use plain Chinese questions. Avoid labels like `required field`, `input schema`, or `parameter`.

## Defaults

- Timeline type: `auto`.
- Output language: Chinese.
- Output format: local editable `.xlsx`.
- Internal team name: `睿丛`.
- Version: client-facing unless the user says internal.
- Client short name: infer from the client or brand name.
- If date constraints are incomplete, create a draft with visible assumptions instead of blocking.

## Inference Rules

- Proposal with clear final delivery but no small times: build backward from final delivery and reserve time for report writing, client feedback, and final polish.
- Proposal with a rough timeline: keep its phase order and big time as the backbone, then add small times for design, recruitment, fieldwork setup, execution, analysis, reporting, feedback, and final polish.
- Delivery, confirmation, submission, communication, and feedback nodes must be working days. Avoid weekends and official public holidays; move non-fixed client-facing nodes earlier to the previous practical working day.
- Proposal with methods but no fieldwork date: place fieldwork after research design and recruitment confirmation, then leave analysis/reporting time before final delivery.
- Digital diary: include setup, respondent onboarding, filling period, progress monitoring, and diary material review.
- IDI/FGD/ethnography: include guide confirmation, fieldwork schedule, client observation option, recap, and transcript/material organization.
- White paper, trend, or strategy studies: include desk research, social/iWOM scan, expert or KOL interviews when relevant, staged findings, topline alignment, and report iteration.
- Complex recruitment: add recruitment condition alignment, respondent profile review, rolling replacement, and schedule updates.
- Multiple methods or many client touchpoints: prefer `work-plan` in `auto` mode.
