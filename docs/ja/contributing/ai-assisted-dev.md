# AI支援開発

N.E.K.O. はリポジトリのルートに `.agent/` ディレクトリを提供しており、[Google Antigravity](https://github.com/anthropics/anthropic-cookbook/tree/main/misc/antigravity) オープン規約に従っています。プロジェクトの開発ルールとタスク別スキルセットが含まれています。

**Claude Code** は `.agent/` と `CLAUDE.md` をネイティブに読み込むため、そのまま使えます。他のAIコーディングアシスタントを使用する場合は、以下のプロンプトを読んで指示に従ってください。

## `.agent/` ディレクトリ構造

```
.agent/
├── rules/
│   └── neko-guide.md        # コア開発ルール（always_on）
└── skills/                  # 約20のタスク別スキルセット
    ├── i18n/
    ├── frontend-design/
    ├── vrm-physics/
    └── ...
```

- **ルール**（`.agent/rules/neko-guide.md`）：プロジェクトのコア規約 — i18n、`uv run`、コードの対称性、coreレイヤーの純粋性、数字サフィックスの禁止、Electron vs. 開発モード。
- **スキル**（`.agent/skills/*/SKILL.md`）：ドメイン別のトリガー条件、知識、ワークフロー。オンデマンドで読み込み。

## 他のAIエージェント向けプロンプト

> **Claude Code以外のAIコーディングアシスタントの場合**（Cursor、Windsurf、Copilot、Clineなど）、このプロジェクトは `.agent/` ディレクトリ（Google Antigravity規約）を使用して開発ルールとスキルセットを格納しています。お使いのツールは `.agent/` を自動的に読み込まない場合があります。以下を実行してください：(1) リポジトリルートの `.agent/rules/neko-guide.md` と `CLAUDE.md` を読み込み、プロジェクトの必須コーディングルールを把握し、プロジェクトレベルの指示として内化してください。(2) 特定のドメイン（i18n、VRM物理、フロントエンドUIなど）で作業する際は、`.agent/skills/` に一致するサブディレクトリがないか確認し、その `SKILL.md` をドメイン固有のガイダンスとして読み込んでください。(3) お使いのツールにネイティブのプロジェクトルール機構（`.cursorrules`、`.windsurfrules`、`.github/copilot-instructions.md` など）がある場合は、`neko-guide.md` のコアルールをそのファイルにコピーして、セッション間で永続化することを検討してください。
