# Timeline Style Guide

## Purpose

Timeline is for internal execution management and for managing client expectations with steady delivery. It should show the project path from kickoff to delivery, key nodes, and responsibility split.

In most cases, the proposal already contains a rough timeline. The client-facing timeline should refine that proposal timeline: keep the proposal's big time, then add small times, detailed tasks, client actions, and delivery checkpoints.

## Core Logic

Always separate:

- Big time: contractual or proposal-level milestones, client business deadlines, kickoff, fieldwork window, Topline, report delivery, final presentation.
- Small times: task-level work needed to hit big time, such as screener revision, recruitment profile updates, guide review, fieldwork scheduling, recap, analysis, and report iteration.
- Date granularity: use day-by-day date columns by default. Use week/month buckets only when the user explicitly asks or when a long project would become unreadable.
- Task blocks: major workstreams such as research design, recruitment, fieldwork, analysis, reporting.
- Task breakdown: concrete actions within each block.
- Responsibility split: what the internal team does, what the client needs to confirm or support, and what the client only needs to know.

Never casually discard the proposal's phase order or milestone dates. If the proposal timing is too compressed, preserve it as the stated constraint and flag the risk in chat before changing it.

## Standard Work Blocks

Use only blocks that match the project:

- Kickoff and scope confirmation.
- Background/proposal review.
- Research design and sample logic.
- Screener or recruitment condition confirmation.
- Recruitment and respondent profile review.
- Interview guide, diary task, or discussion guide design.
- Fieldwork arrangement and execution.
- Daily or rolling progress update.
- Fieldwork recap or staged findings.
- Analysis and framework building.
- Topline delivery and alignment.
- Full report writing.
- Final report delivery and presentation.
- Report optimization and follow-up.

## Work Plan Format

Use `assets/work-plan-template.xlsx` for the explanatory pure table work plan when the client needs frequent cooperation or the project needs more words to clarify how tasks connect.

Column behavior:

- `阶段`: concise phase name, merged vertically.
- internal action: concrete work product or action by the internal team.
- client action: one of `/`, `意见反馈`, `确认`, `协助提供资料`, `协助邀约`, `可参与旁听`, `可查看后台进度`, or a short concrete request.
- `时间`: short Chinese date phrase.
- `备注`: why this matters, what will be updated, how the collaboration works, or what expectation should be aligned.

## Standard Gantt Format

Use `assets/gantt-template.xlsx` for the table + gantt timeline when the user needs a compact schedule view.

Required visual elements:

- title with project name.
- fixed left task table: `Task Sections`, `Work Content`, `Note`, `Deliver date`.
- visible legend: yellow block = `Working process`; green block = `Delivery`.
- date grid by day to the right of the task table unless the user explicitly requests another granularity or the project is too long to read.
- grouped phase/task rows.
- yellow bars for working-process duration.
- green marks only on delivery / submission / confirmation days.
- legend.
- owner/client involvement columns.

Use day columns by default. For longer projects, keep daily columns if still readable; switch to week columns only when necessary or requested, and preserve exact milestone dates in labels.

Template behavior:

- Keep the bilingual style if the source project or client-facing expectation uses English; otherwise Chinese-only task names are acceptable.
- Use bilingual Chinese/English task names, notes, and client actions for foreign-company clients. Use Chinese-only output for domestic Chinese clients.
- Keep yellow for process bars and green for delivery / confirmation / submission date cells.
- Do not mark fieldwork or IDI tasks red by default. Interviews are process work unless the user or proposal makes that specific interview date a client-facing delivery/critical milestone.
- Keep delivery/confirmation rows visually distinct only when they are true client-facing milestones. Do not use red as the default milestone color.
- Keep holiday blocks when relevant; replace or remove them if the project does not cross a holiday.
- Replace placeholder task rows rather than copying source project content.

## Date and Buffer Rules

- Respect proposal big time before optimizing small times.
- Use the proposal rough timeline as the backbone when present.
- Give work blocks enough time to be credible. Do not stack recruitment, fieldwork, analysis, and report delivery unrealistically unless the user explicitly provides that constraint.
- Add buffer around holidays, major feedback rounds, and report finalization.
- Place delivery, submission, confirmation, and client feedback nodes on working days. Avoid weekends and official public holidays. If a milestone would fall on a non-working day, move it to the previous practical working day unless the user says it is fixed.
- Use `前` for deadlines, `递交` for submissions, `确认` for approval nodes, and ranges for execution.

## Client-Facing Tone

Use stable, consultative language. Avoid sounding like a rigid task tracker or exposing internal panic.

Preferred ideas:

- align early.
- roll updates forward.
- maintain information consistency.
- support staged confirmation.
- continue validating and iterating in later research.
- clarify which items need client action.
