# BLCaptain Study Loop

[中文](./README.md) | **English**

BLCaptain Study Loop is a goal-driven Codex learning workspace. It turns a regular "I want to learn this" conversation into a workflow with goals, sources, practice, evidence, reusable artifacts, and stage reviews.

It is built for people who do not just want an explanation. They need to learn, build, explain, pass, or ship something under a real deadline.

## Contents

- [Why It Exists](#why-it-exists)
- [What It Is](#what-it-is)
- [What Problems It Solves](#what-problems-it-solves)
- [How It Differs From A Normal Agent Chat](#how-it-differs-from-a-normal-agent-chat)
- [Value](#value)
- [Who It Is For](#who-it-is-for)
- [Installation](#installation)
- [Example Flow](#example-flow)
- [Repository Layout](#repository-layout)
- [Examples](#examples)
- [FAQ](#faq)
- [About The Author](#about-the-author)

## Why It Exists

Many AI learning chats fail not because the model cannot explain, but because the learning process is not organized:

- You read a lot, but cannot tell what you can actually do.
- Sources are mixed together without trust levels or clear purpose.
- Context disappears between sessions.
- Learning goals do not become deliverables, exercises, or checklists.
- Agents often produce plans, but do not push toward something usable today.

BLCaptain Study Loop helps Codex maintain a learning workspace that can continue across sessions and prove progress with evidence.

## What It Is

It is a Codex skill that maintains these artifacts around a concrete learning goal:

- `LEARNING-BRIEF.md`: Captures the goal, deadline, deliverable, constraints, and non-goals.
- `SOURCEBOOK.md`: Tracks trusted sources, source type, accessibility, and risk.
- `lessons/*.html`: Local HTML micro-lessons, each focused on one practiceable capability.
- `cards/*.html`: Reusable reference cards, process cards, terminology cards, or checklists.
- `progress/*.md`: Progress records backed by practice evidence.
- `TERMS.md`: A glossary for shared terminology and domain terms.
- `REVIEWS.md`: Stage reviews, blockers, next steps, and strategy changes.

It is not a course platform or a chat template. It is closer to an operating workflow for agent-assisted learning: define the target, collect sources, practice one small capability, then decide whether progress is real.

## What Problems It Solves

- Turns "I want to learn X" into an executable learning target.
- Organizes scattered sources by trust level and use case.
- Breaks long explanations into lessons that can be practiced and reviewed.
- Replaces vague confidence with E0 to E3 evidence levels.
- Converts one-off answers into files that can be reused later.
- Handles real teams, products, source constraints, and delivery scenarios.

## How It Differs From A Normal Agent Chat

| Dimension | Normal agent chat | BLCaptain Study Loop |
| --- | --- | --- |
| Goal | Often starts from a question and drifts | Writes a learning brief with goal, deadline, deliverable, and boundaries |
| Sources | Ad hoc references with mixed quality | Uses `SOURCEBOOK.md` to track trust level, purpose, accessibility, and risk |
| Teaching | Often explains too much at once | Advances one practiceable capability per loop |
| Progress | "Covered" can feel like "learned" | No `progress/` record without E2/E3 evidence |
| Output | Mostly answer text | Produces lessons, cards, checklists, reviews, and records |
| Continuity | Depends on chat history | Continues from workspace files |
| Context | Often generic examples | Uses practical work scenarios and accessible sources |

## Value

- For individuals: move faster from "I understand" to "I can use it".
- For teams: turn learning sessions into reusable materials.
- For agent users: give Codex a clear operating track and reduce fake progress.
- For open-source collaborators: keep the structure understandable, verifiable, and easy to adapt.

## Who It Is For

Good fit for:

- PMs, founders, operators, designers, and engineers who need to build a capability quickly.
- People preparing for interviews, exams, demos, reviews, or internal sharing.
- Teams turning sources into lessons, cards, checklists, or internal knowledge.
- People building their own Codex skills, agent workflows, or AI workbenches.
- People working across local team context and primary source materials.

Not a good fit for:

- One-off factual questions.
- Users who do not want workspace files.
- Full LMS, database, account system, or course backend needs.
- Situations where you want the agent to declare progress without practice evidence.

## Installation

Copy the `skill/` directory into your Codex skills directory and name it `blcaptain-study-loop`:

```bash
mkdir -p ~/.codex/skills/blcaptain-study-loop
cp -R skill/. ~/.codex/skills/blcaptain-study-loop/
```

Restart Codex, then use:

```text
Use $blcaptain-study-loop I want to learn how to write a usable Codex skill in one day.
```

## Example Flow

You can start with:

```text
Use $blcaptain-study-loop 我想一天内做出一个根据图片生成视频分镜提示词的 skill，要求今天能试用。
```

Expected flow:

1. Decide whether the goal is specific enough. If not, ask at most 3 key questions.
2. Create or update `LEARNING-BRIEF.md` with today's deliverable and non-goals.
3. Create `SOURCEBOOK.md` with primary sources and high-quality references.
4. Produce the first practiceable lesson or a hands-on checklist.
5. Produce a reusable card when useful, such as a skill scope card or prompt checklist.
6. Run a forward test using a real or simulated input.
7. Record progress only when the user reaches E2/E3 evidence.
8. Update `REVIEWS.md` with the stage review and next step.

## Repository Layout

The actual skill lives in [`skill/`](./skill/):

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

Repository-level files:

```text
.
├── README.md
├── README.en.md
├── LICENSE
├── skill/
└── examples/
```

## Examples

This repository includes three example workspaces:

- [`examples/01-technical-understanding`](./examples/01-technical-understanding): Explain `useEffect` dependency arrays in 30 minutes.
- [`examples/02-delivery-project`](./examples/02-delivery-project): Build an image-to-video storyboard prompt skill in one day.
- [`examples/03-interview-prep`](./examples/03-interview-prep): Prepare for a 20-minute RAG interview.

Each example includes a learning brief, sourcebook, lesson, card, progress record, and review.

## Positioning

Recommended public positioning:

> BLCaptain Study Loop is a goal-driven Codex learning workspace with evidence-gated progress, reusable learning artifacts, trusted sources, and stage reviews.

After installation, restart Codex or open a fresh session and confirm `$blcaptain-study-loop` is discovered and follows goal routing.

## FAQ

### Is this just a prompt?

No. It is a Codex skill. The core value is not a single prompt, but a repeatable workflow for creating, updating, and validating learning artifacts.

### Does it automatically decide that I have learned something?

No. Progress requires evidence. Covered is E0, restated is E1, applied in practice is E2, and transferred to a new context is E3.

### Why does it write multiple files?

To make learning resumable across sessions. Goals, sources, lessons, cards, progress, and reviews each have a clear place.

### Can it use multilingual sources?

Yes. It is designed to use primary sources such as official docs, source code, papers, and specifications, while organizing the learning process in the user's working language.

### How is it different from a normal course?

A normal course usually follows a knowledge structure. BLCaptain Study Loop follows a real target: what needs to be delivered, practiced, or proven next.

### How is it different from a normal agent chat?

A normal chat is mostly immediate Q&A. This skill maintains workspace files and uses evidence gates to prevent fake learning progress.

### Can I adapt it for my team?

Yes. Keep goal routing, evidence levels, `SOURCEBOOK.md`, and `REVIEWS.md` first. Then replace terminology, source rules, and deliverable templates for your team.

## About The Author

**爆裂队长NEXT**

15yr PM. Fired myself. Hired 10 AIs. Turns out managing AIs is harder than managing humans.

AI Agents BLTeam 翻车笔记。真实战，生产级真干货持续分享。少刷二手情绪，多看一手信号源。

- X/Twitter: [@thinkszyg](https://x.com/thinkszyg)
- Email: [blteam2026@outlook.com](mailto:blteam2026@outlook.com)
