# Agent Skills

个人可复用 Agent Skills 仓库。每个 skill 都是独立目录，可被兼容 Agent Skills 标准的工具发现和安装。

## 当前 skills

- `develop-fastapi-endpoint`：按目标项目约定设计、实现、重构和审查生产级 FastAPI 接口。
- `docs-cleanup`：在开发阶段结束后清理项目文档，保留可长期复用的当前状态、架构、决策、约束和待办。
- `plan-gate`：在实施前审核指定方案的项目一致性、职责边界、完整性、MVP 和可执行性，通过后方可进入实施。
- `plan-split`：在实施前检查方案规模，并将过大的方案拆成可独立执行和验证的顺序任务。

## 仓库结构

```text
skills/
├── develop-fastapi-endpoint/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
│       ├── architecture.md
│       └── review-checklist.md
├── docs-cleanup/
│   ├── SKILL.md
│   └── agents/openai.yaml
├── plan-gate/
│   ├── SKILL.md
│   └── agents/openai.yaml
└── plan-split/
    ├── SKILL.md
    └── agents/openai.yaml
```

后续能力继续添加到 `skills/<skill-name>/`，每个目录必须包含带 `name` 和 `description` frontmatter 的 `SKILL.md`。

## 本地检查

在仓库根目录运行：

```bash
npx skills add . --list
```

## 安装

```bash
# 查看仓库中可安装的 skills
npx skills add fuweihang/skills --list

# 全局安装指定 skill，并将其配置给 Codex
npx skills add fuweihang/skills --skill plan-split -a codex -g
```

省略 `--skill <name>` 可选择安装多个 skill；去掉 `-g` 可安装到当前项目；增加 `-y` 可跳过交互确认。
