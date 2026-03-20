# 記事作成プラン: Git Worktree後にCursorを自動起動するClaude Code hooks

## Context

Issue #5 の要望: 新しいIssueやPRレビュー開始時にWorktreeを作成した後、毎回手動でエディタを開くのが手間。Claude Code hooksで自動化した体験を記事にする。

既存の実装（`~/.claude/hooks/open-editor-on-worktree.sh`）を基に、Cursor前提で記事を書く。

## 記事構成

前回の記事（fd63a0792d8fe3.md）のスタイルを踏襲: です/ます調、実体験ベース、コード例付き、「はじめに」「おわりに」構成。

### frontmatter
```yaml
title: "Git Worktreeを作ったら自動でCursorが開く！Claude Code hooksで実現した話"
emoji: "🪝"
type: "tech"
topics: ["claudecode", "gitworktree", "cursor", "hooks", "開発効率化"]
published: false  # 初稿なのでfalse
```

### セクション構成

1. **はじめに** — 前回のSkill記事からの繋がり。Worktree Skill紹介時に触れた「Worktree作成後のエディタ起動」の自動化の話
2. **課題: Worktree作成後の手動操作が地味に面倒** — ターミナルでWorktree作成→ディレクトリ移動→Cursor起動の手間、毎回やると積もるストレス
3. **Claude Code hooksとは？** — hooksの基本概念（PostToolUse等）、settings.jsonでの設定方法を簡潔に説明
4. **実装: Worktree作成を検知してCursorを自動起動するhook** — settings.jsonの設定例、シェルスクリプトの実装、各行の解説
5. **動作の流れ** — 実際の使用シーン（Skill経由でWorktree作成→自動でCursorが開く）
6. **ハマりポイント・工夫した点** — 実装時の注意点（stdinからの読み取り、exit 0の重要性など）
7. **おわりに** — hooksとSkillの組み合わせで開発体験が変わる、小さな自動化の積み重ねの価値

## 作業手順

1. mainから新しいブランチを作成（`article/claude-code-hooks-worktree`）
2. `pnpm run new:article` で新規記事ファイル作成
2. frontmatter + 本文の初稿を書く
3. 既存のスクリプト（`~/.claude/hooks/open-editor-on-worktree.sh`）をCursor版に書き換えたコード例を記事に含める

## 参照ファイル
- [fd63a0792d8fe3.md](articles/fd63a0792d8fe3.md) — 前回記事（スタイル参考）
- `~/.claude/settings.json` — hooks設定の実例
- `~/.claude/hooks/open-editor-on-worktree.sh` — フックスクリプトの実装

## 検証
- `pnpm run preview` でローカルプレビュー確認
- frontmatterのバリデーション（必須フィールド、topics数）
