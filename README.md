# Fast Learn

[English](README.md) | [简体中文](README.zh-CN.md)

Fast Learn turns an AI agent into an adaptive private teacher. It builds a proficiency map, extracts the highest-leverage 20%, teaches one step at a time, diagnoses gaps through one-question-at-a-time testing, and verifies mastery through explanation and application.

## What it does

- Adapts to the learner's current level, available effort, and target proficiency.
- Builds a 3–5 level learning map and a focused 80/20 sprint plan.
- Scores each answer and requires at least 85% plus a sound reasoning chain to pass a module.
- Uses Feynman explanations, targeted remediation, and one-page cheat sheets.
- Can teach from supplied repositories, code, or documents without modifying the project.

## Compatibility

| Environment | Support |
| --- | --- |
| Codex | Native `SKILL.md` package with `agents/openai.yaml` metadata. |
| Claude Code | Compatible with the [Agent Skills format](https://code.claude.com/docs/en/slash-commands); a ready-to-copy template is included. |
| Other agents | Likely compatible when the agent supports the Agent Skills standard; discovery and invocation may differ. |

## Install

Clone the repository:

```bash
git clone https://github.com/Perry-ZHENG/A-skill-for-human-fast-learning.git
cd fast-learn
```

### Codex

```bash
mkdir -p ~/.codex/skills
cp -R skills/fast-learn ~/.codex/skills/
```

### Claude Code — personal skill

```bash
mkdir -p ~/.claude/skills
cp -R templates/claude-code/.claude/skills/fast-learn ~/.claude/skills/
```

For a project-only installation, copy the same folder to `<project>/.claude/skills/fast-learn`.

## Use

Tell the teacher four things: the topic, your current level, your available effort, and the outcome you want.

Codex:

```text
Use $fast-learn to help me learn SQL. I know basic spreadsheets, have 10 hours this week, and want to analyze product data independently.
```

Claude Code:

```text
/fast-learn Help me learn SQL. I know basic spreadsheets, have 10 hours this week, and want to analyze product data independently.
```

Fast Learn advances one learning action at a time. It may first calibrate an unrealistic target before creating the learning map.

## Boundaries

Fast Learn teaches, quizzes, diagnoses, and reviews. It does not perform physical practice or implement changes in the learner's project; use a separate coding task for project modifications.

## Repository layout

```text
skills/fast-learn/          Codex and portable Agent Skill
templates/claude-code/      Ready-to-copy Claude Code project template
```

## License

[MIT](LICENSE)
