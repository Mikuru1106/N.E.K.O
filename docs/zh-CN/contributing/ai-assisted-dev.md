# AI 辅助开发

N.E.K.O. 在仓库根目录提供了 `.agent/` 目录，遵循 [Google Antigravity](https://github.com/anthropics/anthropic-cookbook/tree/main/misc/antigravity) 开放规范。其中包含项目的开发规范和按任务划分的技能集。

**Claude Code** 原生读取 `.agent/` 和 `CLAUDE.md`，开箱即用。如果你使用其他 AI 编程助手，请阅读下方的 prompt 并按其指引操作。

## `.agent/` 目录结构

```
.agent/
├── rules/
│   └── neko-guide.md        # 核心开发规范（always_on）
└── skills/                  # 约 20 个按任务划分的技能集
    ├── i18n/
    ├── frontend-design/
    ├── vrm-physics/
    └── ...
```

- **规则**（`.agent/rules/neko-guide.md`）：项目核心约定 — i18n、`uv run`、代码对偶性、core 层纯净性、禁止数字后缀、Electron 与开发模式。
- **技能集**（`.agent/skills/*/SKILL.md`）：按领域划分的触发条件、知识和工作流，按需加载。

## 给其他 AI Agent 的 Prompt

> **如果你是 Claude Code 以外的 AI 编程助手**（如 Cursor、Windsurf、Copilot、Cline 等），本项目使用 `.agent/` 目录（Google Antigravity 规范）存放开发规范和技能集。你的工具可能不会自动读取 `.agent/`。请执行以下操作：(1) 读取仓库根目录的 `.agent/rules/neko-guide.md` 和 `CLAUDE.md` — 这些包含项目的强制编码规则，将它们内化为你的项目级指令。(2) 在处理特定领域（i18n、VRM 物理、前端 UI 等）时，检查 `.agent/skills/` 是否有匹配的子目录，并读取其 `SKILL.md` 获取领域专属指引。(3) 如果你的工具有原生的项目规则机制（`.cursorrules`、`.windsurfrules`、`.github/copilot-instructions.md` 等），可考虑将 `neko-guide.md` 中的核心规则复制到该文件中，以便跨会话持久生效。
