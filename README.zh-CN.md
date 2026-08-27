# Fast Learn

[English](README.md) | [简体中文](README.zh-CN.md)

Fast Learn 把 AI Agent 变成自适应私人老师：先搭建能力地图，再提取最有杠杆的核心 20%，一次推进一个学习动作，通过逐题诊断、复述和应用检验真实掌握程度。

## 主要能力

- 根据用户当前水平、可用精力和目标等级调整教学深度。
- 生成 3–5 级学习地图与聚焦核心 20% 的短期计划。
- 每题具体评分；模块通关要求综合达到 85% 以上且关键逻辑正确。
- 支持费曼复述、针对性补缺和模块一页速查表。
- 可结合用户提供的代码库、代码或文档教学，但不会直接修改项目。

## 适配环境

| 环境 | 支持情况 |
| --- | --- |
| Codex | 原生 `SKILL.md` 包，并包含 `agents/openai.yaml` 界面元数据。 |
| Claude Code | 兼容官方 [Agent Skills 格式](https://code.claude.com/docs/en/slash-commands)，仓库内提供可直接复制的模板。 |
| 其他 Agent | 支持 Agent Skills 标准时通常可用，但发现和调用方式可能不同。 |

## 安装

克隆仓库：

```bash
git clone https://github.com/Perry-ZHENG/A-skill-for-human-fast-learning.git fast-learn
cd fast-learn
```

### Codex

```bash
mkdir -p ~/.codex/skills
cp -R skills/fast-learn ~/.codex/skills/
```

### Claude Code：个人 Skill

```bash
mkdir -p ~/.claude/skills
cp -R templates/claude-code/.claude/skills/fast-learn ~/.claude/skills/
```

如果只想在单个项目中使用，请把同一目录复制到 `<project>/.claude/skills/fast-learn`。

## 使用

告诉老师四项信息：学习主题、当前水平、可用精力和希望达成的结果。

Codex：

```text
使用 $fast-learn 帮我学习 SQL。我会使用基础表格，本周可投入 10 小时，目标是独立分析产品数据。
```

Claude Code：

```text
/fast-learn 帮我学习 SQL。我会使用基础表格，本周可投入 10 小时，目标是独立分析产品数据。
```

Fast Learn 每次只推进一个学习动作。如果目标明显超出可用时间，它会先校准目标，再创建学习地图。

## 能力边界

Fast Learn 负责教学、提问、诊断和评审，不负责实物操演，也不会代替用户修改项目代码；项目修改应放在独立的编码任务中完成。

## 仓库结构

```text
skills/fast-learn/          Codex 与通用 Agent Skill
templates/claude-code/      可直接复制的 Claude Code 项目模板
```

## License

[MIT](LICENSE)
