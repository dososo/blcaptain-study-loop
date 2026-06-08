# BLCaptain Study Loop

**中文** | [English](./README.en.md)

BLCaptain Study Loop 是一个面向 Codex 的目标驱动学习工作台。它把一次普通的“我想学”对话，变成有目标、有资料、有练习、有证据、有复盘的持续学习流程。

它适合那些不是只想听解释，而是真的要在今天、本周或某个截止日期前学会、做出、讲清、交付的人。

## 目录

- [为什么做它](#为什么做它)
- [它是什么](#它是什么)
- [能解决什么问题](#能解决什么问题)
- [和一般 Agent 对话的区别](#和一般-agent-对话的区别)
- [提供的价值](#提供的价值)
- [适合谁](#适合谁)
- [安装](#安装)
- [示例流程](#示例流程)
- [仓库结构](#仓库结构)
- [示例工作区](#示例工作区)
- [FAQ](#faq)
- [关于作者](#关于作者)

## 为什么做它

很多 AI 学习对话的问题，不是模型不会讲，而是学习没有被组织起来:

- 讲过很多，但不知道自己到底会了什么。
- 资料很多，但不知道哪些是一手来源，哪些只是二手经验。
- 上下文很快散掉，下一轮又从头解释。
- 学习目标没有变成可交付产物、练习或检查清单。
- Agent 容易给计划，难以逼近“今天就能用”的结果。

BLCaptain Study Loop 的目标是让 Codex 不只回答问题，而是维护一个可继续、可验证、可复盘的学习工作台。

## 它是什么

它是一个 Codex skill，触发后会围绕一个具体学习目标维护这些产物:

- `LEARNING-BRIEF.md`: 学习任务简报，固定真实目标、期限、产物和边界。
- `SOURCEBOOK.md`: 可信资料清单，区分一手资料、专家资料、社区经验和可获取性。
- `lessons/*.html`: 一节只练一个小能力的本地 HTML 微课。
- `cards/*.html`: 长期可复用的速查卡、流程卡、术语卡或检查清单。
- `progress/*.md`: 只记录已经通过练习证明的学习进展。
- `TERMS.md`: 术语表，统一关键术语和工作语境。
- `REVIEWS.md`: 阶段复盘，记录下一步、阻塞点和策略调整。

它不是课程平台，也不是聊天模板。它更像一个给 Agent 用的学习操作系统: 先定目标，再找资料，再练一个小能力，最后用证据决定是否算掌握。

## 能解决什么问题

- 把“我想学 X”改写成可执行目标和最小交付。
- 把零散资料整理成可信度和用途清楚的来源清单。
- 把长篇解释拆成能练、能测、能复盘的小课。
- 把“我感觉懂了”改成 E0 到 E3 的证据等级。
- 把一次性回答沉淀成下次还能继续使用的文件。
- 把真实团队、产品、资料约束和交付场景纳入学习设计。

## 和一般 Agent 对话的区别

| 维度 | 一般 Agent 对话 | BLCaptain Study Loop |
| --- | --- | --- |
| 目标 | 常从问题开始，容易越聊越散 | 先写学习简报，目标、期限、产物和边界都落盘 |
| 资料 | 临时引用，质量参差不齐 | 用 `SOURCEBOOK.md` 记录来源层级、用途、可获取性和风险 |
| 教学 | 倾向一次讲很多 | 每轮只推进一个可练习的小能力 |
| 进展 | “讲过了”容易被当成“学会了” | 没有 E2/E3 证据，不写入 `progress/` |
| 产物 | 多数停留在回答文本 | 产出 lesson、card、checklist、review 等可复用文件 |
| 连续性 | 依赖聊天历史 | 依赖工作区文件，新会话也能继续接上 |
| 语境 | 常用泛化例子 | 优先贴近真实工作、团队协作和可访问资料 |

## 提供的价值

- 对个人: 更快从“听懂”走到“会用”，适合短周期补能力。
- 对团队: 能把一次学习过程沉淀为可复用材料，减少重复讲解。
- 对 Agent 使用者: 给 Codex 明确的工作轨道，降低上下文漂移和假进展。
- 对开源协作者: 文件结构清楚，便于理解、验证和二次改造。

## 适合谁

适合:

- 产品经理、创业者、运营、设计师、工程师，需要快速补齐某个工作能力。
- 正在准备面试、考试、答辩或内部分享的人。
- 想把资料变成课程、卡片、检查清单或团队知识沉淀的人。
- 正在打造自己的 Codex skills、Agent workflow 或 AI 工作台的人。
- 需要同时处理本地工作语境和一手资料的人。

不适合:

- 只想问一个事实，不需要后续练习或记录。
- 不希望工作区产生任何学习文件。
- 想要完整 LMS、数据库、账号系统或课程后台。
- 希望 Agent 直接替你宣布“学会了”，但不做练习验证。

## 安装

复制 `skill/` 目录到 Codex skills 目录，并命名为 `blcaptain-study-loop`:

```bash
mkdir -p ~/.codex/skills/blcaptain-study-loop
cp -R skill/. ~/.codex/skills/blcaptain-study-loop/
```

重启 Codex 后使用:

```text
Use $blcaptain-study-loop 我想在一天内学会写一个可用的 Codex skill。
```

## 示例流程

你可以这样开始:

```text
Use $blcaptain-study-loop 我想一天内做出一个根据图片生成视频分镜提示词的 skill，要求今天能试用。
```

理想情况下，Codex 会按这个顺序推进:

1. 判断目标是否足够具体，如果模糊，最多问 3 个关键问题。
2. 创建或更新 `LEARNING-BRIEF.md`，明确今天的交付物和不做什么。
3. 创建 `SOURCEBOOK.md`，优先记录官方文档、一手示例和高质量参考。
4. 产出第一节可练习 lesson，或者直接给一个实操清单。
5. 产出一个可长期复用的 card，例如 skill scope card 或 prompt checklist。
6. 做一次 forward test，用真实或模拟输入验证能不能跑通。
7. 只有当你完成练习并达到 E2/E3 证据时，才写入 `progress/`。
8. 在 `REVIEWS.md` 记录阶段复盘和下一步。

## 仓库结构

实际 skill 在 [`skill/`](./skill/) 目录:

```text
skill/
├── SKILL.md
├── LEARNING-BRIEF-FORMAT.md
├── SOURCEBOOK-FORMAT.md
├── PROGRESS-RECORD-FORMAT.md
├── TERMS-FORMAT.md
├── REVIEW-FORMAT.md
├── agents/
│   └── openai.yaml
└── references/
    └── learning-operating-system.md
```

仓库级文件:

```text
.
├── README.md
├── README.en.md
├── LICENSE
├── skill/
└── examples/
```

## 示例工作区

仓库包含三个示例:

- [`examples/01-technical-understanding`](./examples/01-technical-understanding): 30 分钟讲清 `useEffect` 依赖数组。
- [`examples/02-delivery-project`](./examples/02-delivery-project): 一天内做出图片转视频分镜提示词 skill。
- [`examples/03-interview-prep`](./examples/03-interview-prep): 准备 20 分钟 RAG 面试问答。

每个示例都包含学习简报、资料清单、lesson、card、progress 和 review，方便你看清 skill 在不同目标下如何落地。

## 设计说明

推荐公开定位:

> BLCaptain Study Loop is a goal-driven Codex learning workspace with evidence-gated progress, reusable learning artifacts, trusted sources, and stage reviews.

一句话表述:

> BLCaptain Study Loop 是一个目标驱动的 Codex 学习工作台，用练习证据、可复用学习产物、可信资料和阶段复盘推动学习真正落地。

安装后建议重启 Codex 或开启全新会话，确认 `$blcaptain-study-loop` 能被发现并按目标路由工作。

## FAQ

### 这是一个 prompt 吗？

不是。它是一个 Codex skill，重点不是一句提示词，而是让 Agent 按固定工作流创建、更新和验证学习产物。

### 它会自动判断我已经学会了吗？

不会。它只根据证据记录进展。讲过是 E0，能复述是 E1，完成练习或小项目才算 E2，能迁移到新场景才算 E3。

### 为什么要写这么多文件？

不是为了仪式感，而是为了让学习可以跨会话继续。目标、资料、课程、卡片、进展和复盘分别落盘，下一次不用重新解释。

### 可以用多语言资料吗？

可以，而且推荐优先使用官方文档、源码、论文和规范等一手资料。这个 skill 会按用户当前工作语言组织学习过程，同时保留必要原文术语。

### 它和一般课程有什么区别？

一般课程常按知识结构展开。BLCaptain Study Loop 按真实目标展开: 今天要交付什么，就围绕这个交付拆资料、练习和验收。

### 它和一般 Agent 对话有什么区别？

一般对话更像即时问答。这个 skill 会维护工作区文件，并用证据等级阻止“讲过就算会”的假进展。

### 我能改造成自己的团队版本吗？

可以。建议先保留目标路由、证据等级、`SOURCEBOOK.md` 和 `REVIEWS.md`，再替换成你的团队术语、资料规范和交付模板。

## 关于作者

**爆裂队长NEXT**

15yr PM. Fired myself. Hired 10 AIs. Turns out managing AIs is harder than managing humans.

AI Agents BLTeam 翻车笔记。真实战，生产级真干货持续分享。少刷二手情绪，多看一手信号源。

- X/Twitter: [@thinkszyg](https://x.com/thinkszyg)
- 邮箱: [blteam2026@outlook.com](mailto:blteam2026@outlook.com)
