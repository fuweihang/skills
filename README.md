# Agent Skills

个人可复用 Agent Skills 仓库。每个 skill 都是独立目录，可被兼容 Agent Skills 标准的工具发现和安装。

## 当前 skills

- `develop-fastapi-endpoint`：按目标项目约定设计、实现、重构和审查生产级 FastAPI 接口。

## 仓库结构

```text
skills/
└── develop-fastapi-endpoint/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
```

后续能力继续添加到 `skills/<skill-name>/`，每个目录必须包含带 `name` 和 `description` frontmatter 的 `SKILL.md`。

## 本地检查

在仓库根目录运行：

```bash
npx skills add . --list
```

## 发布后安装

将仓库推送到 GitHub 后，把 `<owner>/skills` 替换为实际仓库：

```bash
npx skills add <owner>/skills --list
npx skills add <owner>/skills --skill develop-fastapi-endpoint -a codex -g
```

去掉 `-g` 可安装到当前项目；增加 `-y` 可跳过交互确认。
