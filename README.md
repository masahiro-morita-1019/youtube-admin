# youtube-admin

YouTubeチャンネル制作をGit中心で管理するための軽量ワークスペースです。

このリポジトリでは、動画そのものや音源ファイルではなく、企画、タイトル、説明文、音楽生成プロンプト、サムネイル参考画像、改善メモを管理します。Notionの「YouTube動画管理」は進捗確認や参照用のダッシュボードとして扱い、初期運用ではGitのMarkdownを主な記録元にします。

## 運用方針

- 公開向けのタイトル、説明文、サムネイル文字は英語で作成する。
- 内部メモ、制作ルール、判断基準、プロンプト改善メモは日本語で管理してよい。
- 管理単位は素材単位を中心にし、公開単位の整理は各チャンネルの `video-index.md` に集約する。
- 動画・音源そのものは当面Git管理しない。必要になったら外部ストレージURLやYouTube URLを記録する。
- サムネイル本番画像はYouTube向け16:9を必須にする。既存の3:2画像は参考画像として残す。

## ディレクトリ

```text
common/
  checklists/        共通チェックリスト
  templates/         新規制作で使うテンプレート
channel/
  Driftane/          運営中チャンネルの固有情報
```

## 基本フロー

1. Driftaneの新規動画は `channel/Driftane/new-video-workflow.md` のトリガー文から始める。テーマ未定でも、過去動画と被らないtheme / mood候補の提案から開始できる。
2. `common/templates/video-plan-template.md` を使って新規企画を作る。
3. タイトル候補は `channel/Driftane/assets/titles.md` に追記する。
4. 音楽生成プロンプトは `channel/Driftane/assets/music-prompts.md` に記録する。
5. 説明文は `channel/Driftane/assets/descriptions.md` の型から作る。
6. サムネイルは `common/checklists/thumbnail-checklist.md` と `channel/Driftane/assets/thumbnail-style-guide.md` で確認する。
7. 公開または予約のタイミングで `channel/Driftane/video-index.md` を更新する。

## Notion

既存Notion:

- Parent page: `youtube/動画管理`
- Database: `YouTube動画管理`

初期実装ではNotionを更新しない。Gitで管理した内容を必要に応じてNotionへ手動転記する。
