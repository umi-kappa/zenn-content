# 記事: 業務で使っているClaude CodeのSkillを紹介する

## Context

GitHub Issue #3 に基づき、業務で使っているClaude CodeのSkillを紹介するZenn記事を作成する。
著者は前回の自己紹介記事で「Claude Codeをほぼ毎日使っている」と書いており、その具体的な活用例としてSkill機能を深掘りする記事。

## 制約事項
- `published: true`（即公開）
- 業務固有のSkillは**社名・プロジェクト名をぼかして一般化**する（完全に省くのではなく、「APIスキャフォールド生成Skill」のように抽象化して紹介）
- コード例は**軽め**（Skillのディレクトリ構造やfrontmatterの例を1-2個程度）

## 実装手順

### 1. ブランチ作成
```bash
git checkout -b article/claude-code-skills
```

### 2. 記事ファイル生成
```bash
pnpm run new:article
```

### 3. frontmatter設定 + 記事本文を記述

```yaml
---
title: "業務で使っているClaude CodeのSkillを紹介します"
emoji: "🛠️"
type: "tech"
topics: ["claudecode", "ai", "skill", "フロントエンド", "開発効率化"]
published: true
---
```

### 4. 記事構成（目安: 3500-4500文字）

#### はじめに（200-300文字）
- 前回の自己紹介記事との繋がり（「Claude Codeをほぼ毎日使っている」の続き）
- Claude CodeのSkill機能にハマっていて業務でガッツリ使っている
- この記事で紹介する内容の概要

#### Skillとは？（300-400文字）
- Skillの基本概念: Claude Codeに特定タスクの手順を教えておける仕組み
- Markdownファイルとして配置、Claude Codeが自動的に適切なSkillを選んでくれる
- User-level（`~/.claude/skills/`、自分専用）と Project-level（`プロジェクト/.claude/skills/`、チーム共有）の違い
- 軽いコード例: Skillのディレクトリ構造（SKILL.md + scripts/ + references/）

#### 使っているSkillを紹介（1200-1500文字）— 記事の核

**コード生成系（社名を出さず一般化して紹介）:**
- **APIスキャフォールド生成Skill**: APIエンドポイント追加時にInfra層→Core層→Composable層まで7-8ファイル+テストを一括生成。「`〜のAPIを追加して`と言うだけ」
- **ページスキャフォールド生成Skill**: 新規ページ作成時にモダン環境+レガシー環境のファイルを一括生成+ルーティング設定まで自動化
- **コンポーネント生成Skill**: Vueコンポーネント+Storybookを自動生成。Figma連携でデザインからコードへ

**ワークフロー系:**
- **リリース前QA Issue作成Skill**: MilestoneからIssue収集・分類→QAチーム向けIssueを自動作成→Projectボードに登録。「地味だけど大事なリリース前の定型作業を自動化」
- **PRレビュー用Worktree作成Skill（add-pr-worktree）**: PR番号やURLを渡すだけで、レビュー用のworktreeを作成し依存パッケージのインストールまで自動で完了。レビュー環境のセットアップが一瞬で終わる。使い方の例も軽く載せる（`/add-pr-worktree 123`）
- **Worktree削除Skill（remove-worktree）**: 「レビュー完了」と言うだけでworktreeをクリーンアップして元のリポジトリに戻れる。未コミットの変更がある場合は確認してくれる安心設計
- **Issue対応用Worktree作成Skill（add-worktree）**（Project-level）: Issue番号からブランチ名を自動生成（日本語タイトルも英語スラッグに変換）。派生元ブランチの指定も可能。チーム全員が同じブランチ命名規則でworktreeを作れる

各Skillは詳細仕様ではなく「何が嬉しいか」「before/after」を中心に紹介。
軽いコード例: SKILLのfrontmatter例（name + description）を1つだけ見せる。

#### Skillの作り方（400-500文字）
- **skill-creator** の紹介（「Skillを作るためのSkill」というメタ感）
- 作り方の流れ: やりたいタスクを説明 → ドラフト生成 → 使いながら調整
- 「最初から完璧を目指さなくていい、育てていく感覚」

#### 業務でProjectにお手製Skillをpushするまでの流れ（500-700文字）
Issue構成案のセクション4に対応。実際のワークフローを3ステップで：

1. **User-levelでまず作って試す**: `~/.claude/skills/` に配置。自分だけの環境で試行錯誤。この段階では雑でOK
2. **チームに共有して意見をもらう**: 使い方と合わせて共有→フィードバック→改善
3. **Project-levelに移動してpush**: リポジトリにcommitして全員が使える状態に

User-levelに複数 / Project-levelはまだ少数、という実態がこの段階的プロセスの結果であることに触れる。

#### 今後の展望（200-300文字）
- Project-levelのSkillを増やしたい
- より複雑なワークフローの自動化への挑戦
- 「Skillは育てるもの」

#### おわりに（100-200文字）
- 開発体験が変わった実感
- 読者への呼びかけ
- 著者らしいカジュアルな締め

### 5. 文体・トーンのガイドライン
- 既存記事 [9c717525720aa6.md](articles/9c717525720aa6.md) のカジュアルで親しみやすいトーンを踏襲
- 技術的な内容と個人的なエピソードの混合
- 絵文字は控えめに（既存記事と同程度）
- 「〜です・〜ます」調

### 6. コミット & PR作成（Issue #3 に紐づけ）

## 参考ファイル
- [articles/9c717525720aa6.md](articles/9c717525720aa6.md) - 既存記事（スタイル参考）
- [CLAUDE.md](CLAUDE.md) - 記事フォーマット定義・コマンド
- `~/.claude/skills/*/SKILL.md` - 各Skillの実物（内容の参考、ただし記事ではぼかす）

## 検証方法
- `pnpm run preview` でローカルプレビューを確認し、表示崩れがないことを確認
