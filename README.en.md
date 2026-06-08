# BLCaptain Study Loop: Learning Workspace Skill

[简体中文](README.md) | **English**

[![Version](https://img.shields.io/badge/version-v0.1.0-2f6fed)](VERSION)
[![License: MIT](https://img.shields.io/badge/license-MIT-2ea44f)](LICENSE)
[![Skill](https://img.shields.io/badge/skill-blcaptain--study--loop-7c3aed)](blcaptain-study-loop/SKILL.md)
[![Examples](https://img.shields.io/badge/examples-3_workspaces-f59e0b)](examples/)

BLCaptain Study Loop is a goal-driven learning workspace skill for Codex.

It does not ask AI to explain more. It turns "I want to learn this" into a learning project with goals, sources, practice, cards, progress evidence, and stage reviews.

It is built for people who need to learn, build, explain, pass, or ship something under a real deadline.

## Example

You can start with:

```text
Use $blcaptain-study-loop 我想一天内做出一个根据图片生成视频分镜提示词的 skill，要求今天能试用。
```

It should not stop at a learning plan. It helps Codex create a minimal learning workspace:

- `LEARNING-BRIEF.md`: What needs to be learned, delivered, and excluded.
- `SOURCEBOOK.md`: Trusted sources, purpose, risks, and accessibility.
- `lessons/*.html`: Local HTML micro-lessons, each focused on one capability.
- `cards/*.html`: Reusable reference cards, process cards, or checklists.
- `progress/*.md`: Progress records backed by practice evidence.
- `REVIEWS.md`: Stage reviews, blockers, and next steps.

This repository includes 3 example workspaces:

- [`examples/01-technical-understanding`](examples/01-technical-understanding/): Explain `useEffect` dependency arrays in 30 minutes.
- [`examples/02-delivery-project`](examples/02-delivery-project/): Build an image-to-video storyboard prompt skill in one day.
- [`examples/03-interview-prep`](examples/03-interview-prep/): Prepare for a 20-minute RAG interview.

## What It Can Do

- Turn "I want to learn X" into an executable learning target.
- Organize scattered sources by trust level, purpose, and accessibility.
- Break long explanations into lessons that can be practiced and reviewed.
- Replace vague confidence with E0 to E3 evidence levels.
- Convert one-off answers into files that can be reused later.
- Bring real work, team collaboration, source constraints, and delivery context into learning.

## What You Get

- A clear learning brief instead of a vague wish.
- A sourcebook instead of a pile of links.
- One or more local HTML micro-lessons.
- Reusable reference cards, process cards, or checklists.
- Progress records backed by practice evidence.
- Stage reviews and next actions.

These artifacts live in the workspace, so future sessions can continue from them.

## Core Mechanisms

### Goal Routing

The skill routes the learning goal before choosing the output:

- Delivery: templates, checklists, small projects, forward tests.
- Ability practice: scenario practice, feedback, error correction.
- Conceptual understanding: comparisons, minimal examples, terminology cards.
- Exam/interview preparation: diagnostics, mistake logs, spaced review.
- Creative work: case breakdowns, rewrites, evaluation rubrics.

### Evidence-Gated Progress

Covered is not learned.

- E0 Coverage: explained, seen, or listed.
- E1 Restatement: the user can explain it.
- E2 Application: the user completes a task, judgment, rewrite, or small project.
- E3 Transfer: the user applies it to a new context and catches exceptions.

Only E2 / E3 belongs in `progress/`.

### Visual Output

Lessons and cards are local HTML artifacts by default:

- Open them later.
- Print them.
- Reuse them as team knowledge cards.
- Iterate on them over time.

The result feels more like a quiet learning workbench than a chat transcript.

## Who It Is For

- PMs, founders, operators, designers, and engineers building a capability quickly.
- People preparing for interviews, exams, demos, reviews, or internal sharing.
- Teams turning sources into lessons, cards, checklists, or internal knowledge.
- People building Codex skills, agent workflows, or AI workbenches.
- People who want evidence-backed learning artifacts, not just explanations.

Not a good fit for:

- One-off factual questions.
- Users who do not want workspace files.
- Full LMS, database, account system, or course backend needs.
- Situations where the agent should declare progress without practice evidence.

## Usage Flow

After installation, invoke it like this:

```text
Use $blcaptain-study-loop I want to learn how to write a usable Codex skill in one day.
```

If the goal is specific enough, it should start producing useful artifacts. If the target is vague, it asks at most 3 key questions.

A normal loop looks like this:

1. Clarify the real goal, deadline, deliverable, and boundaries.
2. Build a trusted sourcebook.
3. Produce a small lesson, exercise, checklist, or project.
4. Produce a reusable card when useful.
5. Record progress only when practice evidence exists.
6. Update reviews when the stage changes.

## Installation

Copy `blcaptain-study-loop/` into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R blcaptain-study-loop ~/.codex/skills/
```

Restart Codex or open a fresh session, then use:

```text
Use $blcaptain-study-loop I want to learn a concrete goal.
```

## Skill Structure

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

Repository structure:

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

**Is this just a prompt?**  
No. It is a Codex skill. The core value is not one prompt, but a repeatable workflow for creating, updating, and validating learning artifacts.

**Does it automatically decide that I have learned something?**  
No. Progress requires evidence. Covered is E0, restated is E1, applied in practice is E2, and transferred to a new context is E3.

**Why does it write multiple files?**  
To make learning resumable across sessions. Goals, sources, lessons, cards, progress, and reviews each have a clear place.

**Can it use multilingual sources?**  
Yes. It organizes learning in the user's working language while preserving necessary original terminology.

**Can I adapt it for my team?**  
Yes. Keep goal routing, evidence levels, `SOURCEBOOK.md`, and `REVIEWS.md` first. Then replace terminology, source rules, and deliverable templates for your team.

## Version

Current version: `v0.1.0`

See [`VERSION`](VERSION).

## About The Author

爆裂队长NEXT

15yr PM. Fired myself. Hired 10 AIs. Turns out managing AIs is harder than managing humans.

AI Agents BLTeam 翻车笔记。真实战，生产级真干货持续分享。少刷二手情绪，多看一手信号源。

X/Twitter: [@thinkszyg](https://x.com/thinkszyg)

Email: blteam2026@outlook.com

## License

MIT. See [`LICENSE`](LICENSE).
