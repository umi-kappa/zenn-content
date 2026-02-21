# 記事作成プラン: 自己紹介 + 技術スタック紹介

## Context

Zennを新しく始めるにあたり、最初の記事として自己紹介と技術スタック紹介を書く（GitHub Issue #1）。
GitHubプロフィールの公開情報をベースに、フロントエンド + Claude Code / AI活用を軸にした内容にする。

## 記事メタデータ

```yaml
---
title: "はじめまして！子育て全振りフロントエンドエンジニアがZennはじめます"
emoji: "👋"
type: "idea"
topics: ["自己紹介", "フロントエンド", "claudecode", "ai"]
published: true
---
```

## 記事構成

### 1. はじめに
- Zennを始めた動機（アウトプットの場として）
- この記事の概要

### 2. 自己紹介
- 名前: umi-kappa
- 拠点: 東京
- 子育て全振りフロントエンドエンジニア
- エンジニア歴の概要（JavaScript歴が長い）

### 3. 技術スタック
- **フロントエンド**: JavaScript / TypeScript、Vue.js など（※ユーザーが詳細を追記・調整）
- **AI活用**: Claude Code の利用歴・経験
  - いつ頃から使い始めたか、どのくらい使っているか
  - 普段の開発でどう活用しているか
  - この記事自体もClaude Codeと相談しながら書いている

### 4. 今後Zennで書いていきたいこと
- フロントエンド関連の知見
- Claude Code / AI活用のTips
- 日々の開発で得た学び

### 5. おわりに
- 読者へのメッセージ、フォローの呼びかけ

## 作業手順

1. mainからブランチを作成（例: `article/first-post`）
2. `pnpm run new:article` で記事ファイルを作成
3. 上記構成に沿って記事本文を執筆
4. `pnpm run preview` で表示確認（ユーザーに依頼）
5. コミット & PRを作成

## 対象ファイル

- `articles/` 配下に新規作成される記事ファイル（スラッグはzenn-cliが自動生成）

## 確認方法

- `pnpm run preview` でローカルプレビュー（http://localhost:8000）を起動し、記事の表示を確認
