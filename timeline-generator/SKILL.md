---
name: timeline-generator
description: Generate company-style research project timelines, 工作计划表, 项目时间表, 标准 timeline / 甘特图, and client-facing project work plans through natural-language collaboration with humanities/research users. Use when Codex needs to read a client brief and/or proposal, infer project rhythm, ask only necessary follow-up questions, draft a timeline for confirmation, then produce an editable .xlsx with company wording, task breakdowns, big time / small times, owners, client actions, and milestones.
---

# Timeline Generator

## Overview

Help research users turn a client brief and/or proposal into a client-facing timeline Excel through conversation. Most proposals already contain a rough timeline; treat that rough timeline as the source constraint and refine it into executable small times, collaboration actions, and delivery nodes. Do not require users to fill a structured form. Act like a pragmatic project manager: read the materials, extract the project rhythm, ask a few plain-language questions only when needed, show a text draft first, then create the workbook.

This skill contributes the conversation workflow, company timeline logic, templates, and wording rules. Use the spreadsheet skill for workbook authoring, visual inspection, and export.

## Start Here

1. Read `references/conversation-workflow.md` first. Follow that sequence unless the user explicitly asks to skip straight to Excel.
2. Read `references/input-spec.md` to know what to extract from a brief/proposal and when to ask follow-up questions.
3. Read `references/timeline-style-guide.md` before deciding the timeline type or task structure.
4. Read `references/wording-bank.md` before drafting Chinese task names, client actions, or remarks.
5. If creating a 说明型工作计划 / pure table timeline, use `assets/work-plan-template.xlsx` as the starting workbook and replace placeholders.
6. If creating a 标准 timeline / 表格+甘特图, use `assets/gantt-template.xlsx` as the starting workbook and replace placeholders, date headers, task rows, and gantt bars as needed.

## Default User Experience

Assume most users are research colleagues, not technical operators. Accept natural requests such as:

- `帮我根据这个 proposal 做一个 timeline`
- `客户 brief 和 proposal 都在附件里，帮我出工作计划表`
- `这个项目要给客户一个时间安排，帮我先梳理一下`
- `用 $timeline-generator 做一版标准甘特图`

The user should not need to know input schemas, Excel rules, or internal implementation details.

## Required Interaction Flow

Unless the user has already provided a fully specified schedule, do not immediately generate Excel.

1. Read the attached brief/proposal and extract a compact project understanding. If the proposal contains a rough timeline, preserve its big time and use it as the backbone.
2. Present the understanding in chat: project goal, client/team, methods, sample/recruitment, deliverables, known big time, and unknowns that affect scheduling.
3. Ask whether the client is a foreign company or a domestic Chinese client if this is not clear from the materials. Use bilingual Chinese/English output for foreign-company clients; use Chinese-only output for domestic Chinese clients.
4. Ask at most five plain-language follow-up questions total. Ask fewer when the material is enough. Do not ask about details that can be reasonably inferred or marked as adjustable in the draft.
5. After the user answers, draft a text timeline table in chat first. Make the phases, tasks, client actions, dates, and key assumptions visible.
6. Invite natural-language correction by making it clear the user can say things like `把招募提前`, `客户要看 topline`, `这个不用客户确认`, or `改成甘特图`.
7. Generate the final `.xlsx` only after the user approves the text draft or asks for direct output.

If the user says to skip confirmation, generate the workbook directly but still apply the extraction, inference, and verification rules.

## Timeline Type Decision

Use `work-plan` when the project has high client collaboration, repeated feedback loops, multiple co-creation/alignment moments, or needs explanatory notes for each task. This is the pure table timeline. It is common for white papers, strategic crowd studies, digital diary plus IDI projects, and studies where clients review screeners, samples, fieldwork progress, toplines, and report iterations.

Use `standard-gantt` when the user asks for a standard timeline, 甘特图, 表格+甘特图, project schedule, or a compact time-path view. This format should make task timing, overlaps, milestones, owners, and client involvement visible at a glance.

Use `auto` when the user does not choose. Default to `work-plan` if the materials mention frequent client confirmation, co-creation, many deliverables, complex recruitment, or multiple research methods. Otherwise default to `standard-gantt`.

## Output Requirements

### Work Plan Excel

Use one sheet named `工作安排计划`.

Required columns, in order:

1. `阶段`
2. `{internal_team}团队动作`
3. `需{client_short_name}团队协助动作`
4. `时间`
5. `备注`

Default `internal_team` to `睿丛` unless the user provides another team name.

Keep phases merged vertically in column A. Use three to four phases unless the user supplies another structure:

- `阶段一\n聚焦`: kickoff, business confirmation, background review, research design, sample/recruitment rules, early alignment.
- `阶段二\n执行`: recruitment, guide/screener confirmation, fieldwork, interviews, diary execution, progress updates, staged findings.
- `阶段三\n产出`: analysis, Topline, report writing, full report, final presentation.
- `后续动作`: report optimization, supplementary questions, archive, or follow-up if needed.

### Standard Gantt Excel

Use `assets/gantt-template.xlsx` and create a compact gantt workbook with:

- project title and date range at the top.
- a legend for task bars, milestones, client confirmation points, and holidays/buffers.
- grouped task rows by phase.
- date columns by day for short projects or week for longer projects.
- day-by-day date columns by default unless the user explicitly asks for a weekly/monthly view or the sheet would become unreadable.
- task owner/client involvement notes in fixed columns before the date grid.
- milestones for kickoff, screener/research design confirmation, recruitment complete, fieldwork start/end, Topline, report delivery, and final presentation when applicable.

Respect the proposal's rough timeline and big time first. Add small times to explain how each proposal-level phase will actually happen, where client actions are needed, and how deliverables will be reached. Schedule delivery and confirmation nodes on working days; avoid weekends and official public holidays.

## Drafting Rules

- Use Chinese human-readable dates: `1月5日-23日`, `2月10日前`, `12月25日递交`.
- For foreign-company clients, provide bilingual Chinese/English task names, notes, and client actions. For domestic Chinese clients, use Chinese only.
- Delivery, submission, confirmation, communication, and client feedback dates must not fall on weekends or official public holidays. If a proposal milestone lands on a non-working day, move it to the previous practical working day unless the user explicitly says the date is fixed.
- Translate brief/proposal language into executable project steps. Do not copy vague proposal wording directly into the timeline when a concrete task name is needed.
- Avoid over-promising exact dates when the source only gives a constraint. Use `预计`, `前后`, `待确认`, or a buffer note only when necessary.
- Make client involvement explicit: distinguish `/`, `意见反馈`, `确认`, `协助邀约`, `可参与旁听`, `可查看后台进度`, and `协助提供资料`.
- Do not expose internal-only uncertainty to the client-facing file unless the user asks for an internal version.
- If materials are incomplete, create a reasonable draft and mark only genuinely unresolved items as `待确认`.
- Preserve a steady, collaborative, delivery-oriented tone. Prefer `沟通对齐`, `前置对齐`, `滚动更新`, `阶段性确认`, `达成初步共识`, and `持续验证与迭代优化`.

## Verification

Before final delivery:

- Inspect the populated workbook values and formulas if any.
- Visually render or inspect all non-empty sheets.
- Fix clipped text, unreadable wrapping, broken merges, default blank sheets, or date grid overflow.
- Confirm final workbook is saved as `.xlsx` under the requested output location.

## Distribution Note

This skill is designed to be shared. Do not hardcode local absolute paths or private project names in generated skill files. Keep bundled examples generic and use placeholders such as `{{项目名称}}`, `{{客户简称}}`, and `{{日期范围}}`.
