# BLCaptain Study Loop：学习工作台 Skill

**简体中文** | [English](README.en.md)

[![Version](https://img.shields.io/badge/version-v0.1.0-2f6fed)](VERSION)
[![License: MIT](https://img.shields.io/badge/license-MIT-2ea44f)](LICENSE)
[![Skill](https://img.shields.io/badge/skill-blcaptain--study--loop-7c3aed)](blcaptain-study-loop/SKILL.md)
[![Examples](https://img.shields.io/badge/examples-3_workspaces-f59e0b)](examples/)

BLCaptain Study Loop 是一个给 Codex 用的目标驱动学习工作台。

它不是让 AI 再多讲一点，而是把“我想学”变成可继续推进的学习项目：目标、资料、练习、卡片、进展证据和阶段复盘都会落到文件里。

适合那些不是只想听解释，而是真的要在今天、本周或某个截止日期前学会、做出、讲清、交付的人。

## 示例

比如你可以这样开始：

```text
Use $blcaptain-study-loop 我想一天内做出一个根据图片生成视频分镜提示词的 skill，要求今天能试用。
```

它不会只给一份学习计划，而会推动 Codex 建立一个最小学习工作区：

- `LEARNING-BRIEF.md`：今天到底要学成什么、交付什么、不做什么。
- `SOURCEBOOK.md`：哪些资料可信、用途是什么、风险在哪里。
- `lessons/*.html`：一节只练一个小能力的本地 HTML 微课。
- `cards/*.html`：可复用的速查卡、流程卡或检查清单。
- `progress/*.md`：只有完成练习或小项目后才记录进展。
- `REVIEWS.md`：阶段复盘、阻塞点和下一步。

这个仓库里有 3 个示例工作区：

- [`examples/01-technical-understanding`](examples/01-technical-understanding/)：30 分钟讲清 `useEffect` 依赖数组。
- [`examples/02-delivery-project`](examples/02-delivery-project/)：一天内做出图片转视频分镜提示词 skill。
- [`examples/03-interview-prep`](examples/03-interview-prep/)：准备 20 分钟 RAG 面试问答。

## 它能做什么

- 把“我想学 X”改写成可执行目标和最小交付。
- 把零散资料整理成可信度、用途和可获取性清楚的来源清单。
- 把长篇解释拆成能练、能测、能复盘的小课。
- 把“我感觉懂了”改成 E0 到 E3 的证据等级。
- 把一次性回答沉淀成下次还能继续使用的文件。
- 把真实工作、团队协作、资料约束和交付场景纳入学习设计。

## 你会得到什么

- 一个明确的学习简报，而不是泛泛的学习愿望。
- 一份可信资料清单，而不是临时链接堆。
- 一节或多节本地 HTML 微课。
- 可反复使用的速查卡、流程卡或检查清单。
- 被练习证明过的进展记录。
- 阶段复盘和下一步行动。

这些内容都保存在当前工作区，下一次会话可以继续接上。

## 核心机制

### 目标路由

Skill 会先判断目标类型，再决定产物：

- 交付型：模板、检查清单、小项目、forward test。
- 能力型：场景练习、即时反馈、错误纠正。
- 理解型：概念对比、最小例子、术语卡。
- 考试/面试型：诊断题、错题记录、间隔复测。
- 创作型：案例拆解、改写练习、评价量表。

### 证据门控

不把“讲过”当成“学会”。

- E0 覆盖：讲过、看过、列过资料。
- E1 复述：能解释，但还没应用。
- E2 应用：完成练习、判断、改写或小项目。
- E3 迁移：能迁移到新场景、发现例外、修正策略。

只有 E2 / E3 才写入 `progress/`。

### 视觉输出

微课和速查卡默认是本地 HTML：

- 可以打开复看。
- 可以打印。
- 可以作为团队知识卡片。
- 可以继续迭代。

这让学习结果更像一个安静的工作台，而不是一段聊天记录。

## 适合谁

- 产品经理、创业者、运营、设计师、工程师，需要快速补齐某个工作能力。
- 正在准备面试、考试、答辩或内部分享的人。
- 想把资料变成课程、卡片、检查清单或团队知识沉淀的人。
- 正在打造自己的 Codex skills、Agent workflow 或 AI 工作台的人。
- 不想只听 AI 解释，而是希望留下可验证产物的人。

不适合：

- 只想问一个事实，不需要后续练习或记录。
- 不希望工作区产生任何学习文件。
- 想要完整 LMS、数据库、账号系统或课程后台。
- 希望 Agent 直接替你宣布“学会了”，但不做练习验证。

## 使用流程

安装后，你可以这样叫它：

```text
Use $blcaptain-study-loop 我想在一天内学会写一个可用的 Codex skill。
```

如果目标足够具体，它会直接推进第一轮产物；如果目标还不清楚，它会最多问 3 个关键问题。

一轮正常流程通常是：

1. 明确真实目标、期限、产物和边界。
2. 建立可信资料清单。
3. 产出一个很小的 lesson、练习、清单或小项目。
4. 产出一个可复用 card。
5. 用练习证据判断是否能写入进展。
6. 在阶段变化时更新复盘。

## 安装

把 `blcaptain-study-loop/` 目录放进你的 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R blcaptain-study-loop ~/.codex/skills/
```

重启 Codex 或开启新会话后使用：

```text
Use $blcaptain-study-loop 我想学习一个具体目标。
```

## 目录结构

```text
blcaptain-study-loop/
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

仓库结构：

```text
.
├── README.md
├── README.en.md
├── VERSION
├── LICENSE
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── SECURITY.md
├── blcaptain-study-loop/
└── examples/
```

## FAQ

**这是一个 prompt 吗？**  
不是。它是一个 Codex skill，核心价值不是一句提示词，而是让 Agent 按固定工作流创建、更新和验证学习产物。

**它会自动判断我已经学会了吗？**  
不会。它只根据证据记录进展。讲过是 E0，能复述是 E1，完成练习或小项目才算 E2，能迁移到新场景才算 E3。

**为什么要写这么多文件？**  
不是为了仪式感，而是为了让学习可以跨会话继续。目标、资料、课程、卡片、进展和复盘分别落盘，下一次不用重新解释。

**可以用多语言资料吗？**  
可以。Skill 会按用户当前工作语言组织学习过程，同时保留必要原文术语。

**我能改造成自己的团队版本吗？**  
可以。建议先保留目标路由、证据等级、`SOURCEBOOK.md` 和 `REVIEWS.md`，再替换成你的团队术语、资料规范和交付模板。

## 版本

当前版本：`v0.1.0`

详见 [`VERSION`](VERSION)。

## 关于作者

爆裂队长NEXT

15yr PM. Fired myself. Hired 10 AIs. Turns out managing AIs is harder than managing humans.

AI Agents BLTeam 翻车笔记。真实战，生产级真干货持续分享。少刷二手情绪，多看一手信号源。

X/Twitter: [@thinkszyg](https://x.com/thinkszyg)

邮箱: blteam2026@outlook.com

## License

MIT。详见 [`LICENSE`](LICENSE)。
