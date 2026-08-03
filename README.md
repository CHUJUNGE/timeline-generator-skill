# timeline-generator

`timeline-generator` 是给研究员使用的 Codex skill，用来把客户 brief / proposal 里的粗排期，细化成可以给客户看的项目时间表。

研究员不需要填写表单，也不需要知道 Excel 怎么画甘特图。把材料发给 Codex，用自然语言说“帮我做 timeline”，Codex 会先梳理项目节奏，再确认关键时间点，最后生成 Excel。

## 适合什么时候用

- 客户 brief / proposal 已经有一个大概时间线，需要细化成正式 timeline。
- 需要把 proposal 里的 Week 1 / Week 2 / 田野 / 报告等粗阶段，拆成具体工作动作。
- 需要明确哪些事情是睿丛做，哪些事情需要客户确认、反馈、旁听或协助。
- 需要输出给客户看的 `工作计划表` 或 `表格 + 甘特图 timeline`。

## 如何在 Codex 里安装

如果这个 repo 地址是：

```text
https://github.com/你的组织/timeline-generator-skill
```

在 Codex 新任务里对 Codex 说：

```text
请帮我从这个 GitHub 地址安装 timeline-generator skill：
https://github.com/你的组织/timeline-generator-skill/tree/main/timeline-generator
```

安装成功后，重启 Codex 或开启新任务，输入：

```text
Use $timeline-generator 帮我根据这个 proposal 做 timeline。
```

## 你可以怎么和 Codex 说

```text
帮我根据这个 proposal 做 timeline。
```

```text
帮我根据这个 proposal 做表格 + 甘特图 timeline。
```

```text
今天 kickoff，最终报告 9 月底前交。帮我根据 proposal 细化 timeline。
```

## Codex 会怎么工作

1. 先读 brief / proposal。
2. 找出 proposal 里已有的粗时间线，作为主轴。
3. 梳理项目目标、研究方法、样本、人群、城市和关键交付物。
4. 把粗时间线细化成 small times：研究设计、招募、田野、分析、Topline、报告、修改、终版交付等。
5. 只问少量真正影响排期的问题。
6. 先在聊天里给一版文字版 timeline 草稿。
7. 用户确认或修改后，再生成 Excel。

## 重要规则

- Proposal 里的粗时间线是主轴，不随便重排。
- 交付、确认、反馈、沟通节点默认避开周末和法定节假日。
- 甘特图里蓝色表示 Working process，红色表示 Delivery / 确认 / 递交当天。
- 线上 / 线下一对一深访默认是过程任务，不标红；除非它本身就是正式交付或关键确认节点。

## 产出类型

### 1. 纯表格工作计划

模板：`timeline-generator/assets/work-plan-template.xlsx`

列结构：

- 阶段
- 睿丛团队动作
- 需客户团队协助动作
- 时间
- 备注

### 2. 表格 + 甘特图 timeline

模板：`timeline-generator/assets/gantt-template.xlsx`

左侧是任务表，右侧是日期网格：

- `Working process`：蓝色过程条
- `Delivery`：红色交付 / 确认当天

## 文件架构

```text
timeline-generator-skill/
├── README.md
└── timeline-generator/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   ├── work-plan-template.xlsx
    │   └── gantt-template.xlsx
    └── references/
        ├── conversation-workflow.md
        ├── input-spec.md
        ├── timeline-style-guide.md
        └── wording-bank.md
```

## 维护说明

只维护 `timeline-generator/` 里的 skill 本体。不要把真实客户 proposal、brief、会议纪要或未脱敏项目文件提交到这个 repo。
