# New Video Workflow

Driftaneで新しい動画を作るときの実運用手順です。最初から完璧な情報を揃える必要はなく、テーマだけでも開始できます。

## Trigger

Codexに新規動画案を作らせるときは、次のように依頼します。

```text
Driftaneの新規動画を作ります。
テーマ: {例: Misty Pines / Window Rain / Nebula Voyage}
用途: {例: deep sleep / relaxation / focus / meditation}
雰囲気: {例: calm, dreamy, cinematic, not scary}

以下を提案してください:
- title候補
- 採用推奨タイトル
- Suno prompt
- thumbnail prompt
- thumbnail text
- YouTube description
- video-index.mdに追記する1行
- assets側に追記すべき改善メモ
```

テーマだけで始める場合:

```text
Driftaneの新規動画を作ります。
テーマは「{theme}」です。
タイトル、Suno prompt、サムネイル方針、説明文まで一式提案してください。
```

## Minimum Inputs

最低限必要な入力は1つだけです。

- Theme: 何をイメージした動画か。

あると精度が上がる入力:

- Use: sleep / deep sleep / relaxation / focus / meditation / mindfulness / stress relief
- Mood: calm / dreamy / peaceful / mysterious / cinematic
- Visual motif: forest / rain / ocean / moon / stars / cabin / window / train / snow
- Avoid: 怖くしない、明るすぎない、人を入れない、ネオンを強くしない、など

## Expected Output

Codexから受け取りたい成果物はこの順番です。

1. Title candidates
2. Recommended title
3. Concept memo
4. Suno prompt
5. Thumbnail prompt
6. Thumbnail text
7. YouTube description
8. Checklist notes
9. Git update proposal

## Output Format

````markdown
## Title Candidates

- {Title A} | Deep Sleep Ambient Music
- {Title B} | Healing Sleep Ambient
- {Title C} | Deep Sleep Ambient Music

Recommended: {Title A} | Deep Sleep Ambient Music

## Concept

日本語の制作メモ。

## Suno Prompt

```text
{prompt}
```

## Thumbnail Prompt

```text
16:9 YouTube thumbnail, cinematic dreamy ambient sleep music artwork, ...
```

Thumbnail text:

```text
{TITLE}
DEEP SLEEP AMBIENT MUSIC
```

## YouTube Description

```text
{English description}
```

## Git Updates

- `channel/Driftane/video-index.md`: VID-XXXを1行追加
- `channel/Driftane/assets/titles.md`: 採用タイトルと候補を追記
- `channel/Driftane/assets/music-prompts.md`: 使用プロンプトと結果メモを追記
- `channel/Driftane/assets/descriptions.md`: 採用説明文を追記
- `channel/Driftane/assets/thumbnail-reviews.md`: サムネイル生成後にレビューを追記
````

## Decision Rules

- 公開タイトルと説明文は英語。
- 内部メモと改善メモは日本語でよい。
- タイトルは2〜3語の詩的な英語を優先する。
- 用途が伝わるように `| Deep Sleep Ambient Music` などを付ける。
- サムネイル本番画像は16:9。
- サムネイル文字は英語のみ。
- 人物、顔、ホラー感、強すぎるネオン、原色、情報過多を避ける。
- `NO VOCALS` をサムネイルで大きく主張しない。

## Manual Workflow

1. トリガー文でCodexに新規動画案を依頼する。
2. 提案されたtitle候補から1つ採用する。
3. 採用したSuno promptで音楽を生成する。
4. 生成結果の良かった点、微妙だった点、次回改善点を `assets/music-prompts.md` に追記する。
5. thumbnail promptで16:9サムネイルを生成する。
6. `common/checklists/thumbnail-checklist.md` でサムネイルを確認する。
7. 採用サムネイルを `assets/references/` または今後作る `assets/thumbnails/` に保存する。
8. YouTube説明文を調整して公開または予約する。
9. `video-index.md` にVID、タイトル、テーマ、用途、進捗、参照画像パスを追記する。

## Example Request

```text
Driftaneの新規動画を作ります。
テーマ: Window Rain
用途: deep sleep, relaxation
雰囲気: quiet apartment night, soft rain, warm window light, calm, not lonely

以下を提案してください:
- title候補
- 採用推奨タイトル
- Suno prompt
- thumbnail prompt
- thumbnail text
- YouTube description
- video-index.mdに追記する1行
- assets側に追記すべき改善メモ
```
