# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

<!-- プロジェクトの目的を1-2文で記載 -->

## Key Commands

```bash
# よく使うコマンドを記載
```

## Architecture

### ディレクトリ構造

```
hitonigiri--/
├── README.md
├── CLAUDE.md
├── DEVLOG.md
├── PROJECT_STANDARDS.md
└── .gitignore
```

## Documentation Rules

プロジェクトのドキュメント規約は [PROJECT_STANDARDS.md](./PROJECT_STANDARDS.md) を参照。

### 重要ルール

1. **日々の作業記録** → `DEVLOG.md` に追記
   - README.mdには日々の詳細を書かない
   - 作業日、実施内容、成果、備考を記録

2. **README.md** → プロジェクト概要のみ
   - 安定した情報（セットアップ、構成図等）
   - 変更が少ない内容

3. **コミット時**
   - 意味のある単位でコミット
   - `Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>` を付与

4. **Issue管理**
   - バグ/機能要望 → 個別Issue
   - 進捗管理 → チェックリスト付きトラッキングIssue
