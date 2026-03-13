# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ヒトニギリ研究所のメインリポジトリ。プロジェクト管理・ドキュメント・サブプロジェクトを統括する。

## Repository

- GitHub: `hitoshi-kano-ui/hitonigiri--`
- Branch: `main`
- Protocol: SSH

## Architecture

このリポジトリはモノレポ構成。サブディレクトリが独立したGitリポジトリを持つ場合がある。

| ディレクトリ | 説明 | 独立リポジトリ |
|-------------|------|---------------|
| `orchestrator/` | エージェント統括（家老） | - |
| `orchestrator/teams/SNS/` | SNS投稿管理 | `hitoshi-kano-ui/hitonigiri--SNS` |

## Documentation Rules

詳細は [PROJECT_STANDARDS.md](./PROJECT_STANDARDS.md) を参照。

- **DEVLOG.md** に日々の作業を記録する（README.mdには書かない）
- **README.md** はプロジェクト概要のみ
- コミットメッセージ形式: `<タイプ>: <概要>` (feat/fix/docs/refactor/test/chore)
- コミットに `Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>` を付与
- Issue: バグ→bugラベル、機能要望→enhancementラベル、進捗管理→チェックリスト付きトラッキングIssue

## Context

すべてのエージェントは作業開始前に以下のファイルを参照すること。

- `context/company.md` - 法人基本情報
- `context/persona.md` - 発信思想・スタンス
- `context/glossary.md` - 独自用語定義
