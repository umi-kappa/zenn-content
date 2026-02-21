# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Zenn (https://zenn.dev) の記事・本を管理するコンテンツリポジトリ。GitHub連携によりmainブランチへのpushで自動的にZennに公開される。

## Commands

```bash
# 新しい記事を作成
pnpm run new:article

# ローカルプレビュー (http://localhost:8000)
pnpm run preview
```

## Structure

- `articles/` — 記事ファイル (.md)。ファイル名がスラッグになる
- `books/` — 本のディレクトリ。各本はサブディレクトリとして管理
- zenn-cli を devDependency として使用（記事作成・プレビュー用）

## Zenn記事のフォーマット

記事ファイルはfrontmatter付きMarkdown。以下のフィールドが必須:

```yaml
---
title: "記事タイトル"
emoji: "😸"       # アイキャッチ絵文字（1文字）
type: "tech"      # tech or idea
topics: ["topic1", "topic2"]  # タグ（最大5つ）
published: true   # true で公開
---
```
