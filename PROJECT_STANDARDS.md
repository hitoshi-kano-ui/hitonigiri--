# プロジェクト標準ガイド

このドキュメントは、プロジェクトのドキュメント構成とGitHub運用のルールを定義します。
Claude Code等のAI CLIツールもこのルールに従って作業します。

---

## ドキュメント構成

### 必須ファイル

| ファイル | 用途 | 更新頻度 |
|----------|------|----------|
| **README.md** | プロジェクト概要、セットアップ手順 | 大きな変更時のみ |
| **CLAUDE.md** | AI CLI向けプロジェクト説明 | 構造変更時 |

### 推奨ファイル

| ファイル | 用途 | 更新頻度 |
|----------|------|----------|
| **DEVLOG.md** | 開発ログ、日々の進捗 | 毎日〜週次 |
| **CHANGELOG.md** | バージョン別リリースノート | リリース時 |
| **PROJECT_STANDARDS.md** | 本ファイル（ルール定義） | ルール変更時 |

---

## 各ファイルの役割と記載内容

### README.md

**目的:** プロジェクトの「顔」。初見の人が理解できる概要。

**記載すべき内容:**
- プロジェクト概要（1-2文）
- 現在のステータス（稼働中/開発中/アーカイブ）
- システム構成図
- クイックスタート手順
- 関連ドキュメントへのリンク

**記載しない内容:**
- 日々の作業ログ → DEVLOG.md へ
- 詳細な変更履歴 → CHANGELOG.md へ
- 実装の詳細 → CLAUDE.md または Wiki へ

### DEVLOG.md

**目的:** 開発の日誌。作業内容と進捗を時系列で記録。

**フォーマット:**
```markdown
# 開発ログ (DEVLOG)

## YYYY-MM-DD

### 実施内容
- 作業内容を箇条書き

### 成果・検出状況
- 数値データや結果

### 課題・備考
- 問題点や気づき

---
```

**記載のタイミング:**
- 作業を行った日
- 重要な変更や発見があった時

### CLAUDE.md

**目的:** AI CLI（Claude Code等）がプロジェクトを理解するための説明書。

**記載すべき内容:**
- プロジェクトの目的と構造
- 主要ファイルの役割
- よく使うコマンド
- コーディング規約
- プロジェクト固有のルール

**例:**
```markdown
# CLAUDE.md

## プロジェクト概要
このプロジェクトは〜を目的としています。

## ファイル構成
- src/ - ソースコード
- tests/ - テスト

## コマンド
- npm start - 起動
- npm test - テスト実行

## ルール
- コミットメッセージは日本語OK
- DEVLOG.mdに作業ログを記録すること
```

### CHANGELOG.md

**目的:** バージョン毎の変更点を記録。

**フォーマット (Keep a Changelog形式):**
```markdown
# Changelog

## [1.2.0] - 2026-01-17
### Added
- 新機能A

### Changed
- 機能Bの改善

### Fixed
- バグCの修正

## [1.1.0] - 2026-01-10
...
```

---

## GitHub Issues の運用

### Issue の種類

| ラベル | 用途 | 例 |
|--------|------|-----|
| **bug** | バグ報告 | 「スクリーンショットが保存されない」 |
| **enhancement** | 機能改善・追加 | 「通知フィルタ機能の追加」 |
| **documentation** | ドキュメント | 「README更新」 |
| **question** | 質問・議論 | 「最適な巡回間隔は？」 |

### Issue の書き方

```markdown
## 概要
1-2文で問題/要望を説明

## 詳細
- 具体的な内容
- 再現手順（バグの場合）

## 期待する動作
どうなるべきか

## 関連
- 関連するIssueやファイルへのリンク
```

### トラッキングIssue（進捗管理用）

大きな目標の進捗管理にはチェックリスト付きIssueを使用:

```markdown
## 概要
〜の完了条件を管理

## チェックリスト
- [ ] 条件1
- [x] 条件2（完了済み）
- [ ] 条件3

## 現在のステータス
| 条件 | 状態 |
|------|------|
| 条件1 | 進行中 |
```

---

## Git コミット規約

### コミットメッセージ形式

```
<タイプ>: <概要>

<詳細（任意）>

Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>
```

### タイプ

| タイプ | 用途 |
|--------|------|
| feat | 新機能 |
| fix | バグ修正 |
| docs | ドキュメント |
| refactor | リファクタリング |
| test | テスト |
| chore | その他（設定変更等） |

### 例

```
feat: Add screenshot capture on RESTOCK detection

- Capture product page using html2canvas
- Save to data/screenshots/
- Queue system for batch processing

Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>
```

---

## AI CLI (Claude Code) への指示

Claude Codeと作業する際は、以下を CLAUDE.md に記載しておくと効果的:

```markdown
## プロジェクトルール

1. **ドキュメント更新**
   - 日々の作業はDEVLOG.mdに記録
   - README.mdは概要のみ（詳細はDEVLOGへ）

2. **コミット**
   - 意味のある単位でコミット
   - Co-Authored-Byを付与

3. **Issue管理**
   - バグ/機能要望は個別Issue
   - 進捗管理はトラッキングIssue
```

---

## 新規プロジェクト作成時のチェックリスト

- [ ] README.md を作成（プロジェクト概要）
- [ ] CLAUDE.md を作成（AI CLI向け説明）
- [ ] DEVLOG.md を作成（空のテンプレート）
- [ ] .gitignore を設定
- [ ] 初回コミット
- [ ] GitHub リポジトリ作成 & プッシュ

---

## 参考

- [Keep a Changelog](https://keepachangelog.com/)
- [Conventional Commits](https://www.conventionalcommits.org/)
