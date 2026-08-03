# Conversation Workflow

Use this workflow for research colleagues who want a timeline from a client brief and/or proposal.

## Principle

Make the interaction feel like working with a project manager, not filling a system form. The user may only say “帮我做 timeline” and upload materials. Your job is to infer, structure, and ask only what is necessary.

Most proposals already include a rough timeline. Treat that proposal timeline as the backbone. The task is usually not to invent a new timeline, but to refine the proposal's big time into small times, concrete tasks, client collaboration actions, and delivery milestones.

## Step 1: Read Materials First

The usual pre-timeline inputs are:

- client brief only.
- proposal only.
- both client brief and proposal.

Do not assume a screener, guide, sample table, or meeting notes exist. Use them only if the user provides them.

Extract:

- project name and client/team.
- project purpose and business/research questions.
- research methods.
- sample size, city/segment coverage, respondent types, or recruitment complexity.
- project start/kickoff clues.
- final delivery, presentation, launch, or client business deadline.
- deliverables promised in the proposal.
- client collaboration moments stated or implied.
- holidays, fixed client review windows, or other immovable dates.

If a proposal includes a timeline page, table, gantt, milestone list, or project schedule paragraph, extract it first and keep it visible in your thinking. Do not overwrite proposal-level timing unless the user asks or the schedule is internally impossible.

## Step 2: Present Project Understanding

Before asking questions, summarize what you found in concise Chinese.

Use this shape:

```text
我先按材料理解到的项目节奏是：

1. 项目目标：
2. 研究方法：
3. 样本 / 城市 / 人群：
4. 关键交付物：
5. 已知大时间点：
6. Proposal 里已有的粗时间线：
7. 我会把它细化成这些 small times：
8. 还会影响 timeline 的信息：
```

Keep it short. The purpose is alignment, not a full proposal summary. Make clear which dates come from the proposal and which are your inferred refinements.

## Step 3: Ask Only Necessary Questions

Ask at most five questions in one turn. Use natural language, not a form. Ask fewer if the proposal already answers enough.

Prioritize these questions:

1. `项目预计什么时候 kickoff / 启动？`
2. `最终报告或汇报有没有已经锁定的日期？`
3. `客户需要高频参与吗，比如确认招募条件、看受访者名单、旁听访谈、看 Topline？`
4. `中间有没有必须给客户看的节点，比如研究设计、Topline、阶段性小结？`
5. `有没有节假日、客户内部会、老板汇报、上市/发布等不能动的时间点？`

If the proposal already has a rough timeline, do not re-ask for those dates. Ask only about missing constraints needed to refine the rough timeline. Do not ask for every missing detail. If a detail can be inferred, draft it and mark the assumption in chat.

When drafting dates, never place delivery, submission, confirmation, or client feedback nodes on weekends or official public holidays. If a rough proposal milestone falls on a non-working day, tell the user you will move the client-facing node to the previous practical working day unless it is fixed.

## Step 4: Draft Text Timeline First

After the user answers, produce a text draft before Excel.

Use a simple Markdown table:

| 阶段 | 睿丛团队动作 | 需客户团队协助动作 | 时间 | 备注 |

For a gantt request, use:

| 阶段 | 任务 | 负责人/协作 | 时间 | 关键节点 |

After the table, add a short `默认假设` list only for assumptions that materially affect timing.

When the proposal has a rough timeline, add a short line before the table:

```text
我会以 proposal 中的粗时间线为主轴，下面主要是在每个阶段下补 small times 和协作节点。
```

## Step 5: Support Natural-Language Revision

Users may revise informally. Interpret and update the timeline without requiring structured edits.

Examples:

- `把招募提前一点` means shift recruitment earlier and adjust dependent tasks.
- `客户要看 topline` means add Topline delivery and alignment before full report.
- `这个不用客户确认` means change client action to `/` or `知晓即可`.
- `最终汇报提前到周五` means compress or move report-writing and finalization steps.
- `做成甘特图` means switch output type to `standard-gantt`.
- `更客户友好一点` means soften remarks and make client actions clearer.
- `深访不用标红` means treat IDI as normal process work unless it is a formal delivery/confirmation node.

If a requested change creates schedule risk, state the risk briefly and propose a workable version.

## Step 6: Create Excel

Generate `.xlsx` only when:

- the user approves the text draft.
- the user asks for direct output.
- the user says the draft is broadly OK and only minor wording remains.

For work plans, start from `assets/work-plan-template.xlsx`. For gantt, create a new workbook following `timeline-style-guide.md`.

## Step 7: Final Response

Keep the final message simple:

- say the Excel is created.
- mention the output path/citation according to the active spreadsheet rules.
- summarize any important assumptions or timing risks in one or two sentences.

Do not describe implementation details, script names, or internal package files unless the user asks.
