# New Video Workflow

Driftaneで新しい動画を作るときの実運用手順です。最初から完璧な情報を揃える必要はなく、テーマ未定でも開始できます。

## Trigger

Codexに新規動画案を作らせるときは、次のように依頼します。

```text
Driftaneの新規動画を作ります。
過去動画と被らないテーマを3〜5案出してください。
しばらくは睡眠向けを優先してください。

以下を提案してください:
- theme候補
- mood候補
- 採用推奨theme / mood
- title候補
- 採用推奨タイトル
- Suno prompt 5案
- thumbnail prompt
- thumbnail text
- YouTube description
- video-index.mdに追記する1行
- assets側に追記すべき改善メモ
```

テーマだけ指定して始める場合:

```text
Driftaneの新規動画を作ります。
テーマは「{theme}」です。
タイトル、Suno prompt 5案、サムネイル方針、説明文まで一式提案してください。
```

## Minimum Inputs

最低限必要な入力はありません。テーマ未定でも開始できます。

デフォルトでは、Codexが `video-index.md` と `assets/titles.md` を確認し、過去動画と被らないthemeを提案します。しばらくはsleep / deep sleep向けのmoodを優先します。

あると精度が上がる入力:

- Theme: 使いたいテーマがある場合。
- Use: sleep / deep sleep / relaxation / focus / meditation / mindfulness / stress relief
- Mood: calm / dreamy / peaceful / mysterious / cinematic
- Visual motif: forest / rain / ocean / moon / stars / cabin / window / train / snow
- Avoid: 怖くしない、明るすぎない、人を入れない、ネオンを強くしない、など

## Theme Proposal Rules

テーマ提案から始める場合、Codexは先に次のファイルを確認します。

- `channel/Driftane/video-index.md`: 過去に採用した動画テーマを確認する。
- `channel/Driftane/assets/titles.md`: 既存タイトルとテーマ案を確認する。
- `channel/Driftane/assets/thumbnail-style-guide.md`: Driftaneらしい世界観を確認する。

テーマ案は次の条件で出します。

- VID-001〜VID-004の主要テーマと丸被りしない。
- しばらくはsleep / deep sleep向けに寄せる。
- 怖さや孤独感より、安心感、静けさ、没入感を優先する。
- タイトル化しやすい2〜3語の英語にする。
- サムネイル化しやすい具体的な絵が浮かぶテーマにする。
- 既存のmoon / rain forest / ocean space / all-nature collageと近すぎる場合は避ける。

優先しやすい候補カテゴリ:

- quiet indoor rain: Window Rain, Cozy Cabin Storm, Quiet Apartment Night
- soft seasonal nature: Snowfall Silence, Autumn Fireplace, Spring Night Breeze
- calm travel ambience: Rainy Train Ride, Moonlit Harbor
- gentle fantasy nature: Spirit Garden, Crystal Cave, Floating Isles
- focused night city: Tokyo After Rain, Rooftop Ambience

デフォルトのmood:

- Sleep
- Calm
- Peaceful

必要な場合だけ追加するmood:

- Focus
- Mysterious

## Suno Prompt Rules

1日で作れる曲は5種類までなので、採用theme / moodが決まったらSuno promptは5案出します。

- 5案は同じthemeを共有しつつ、音の方向性を少しずつ変える。
- しばらくはsleep / deep sleep向けを優先する。
- すべてno vocals前提にする。
- 1案ごとに狙いを1行で書く。
- 5案のうち、採用推奨を1つ選ぶ。
- 生成後に、良かった点、微妙だった点、次回改善点を `assets/music-prompts.md` に残す。

5案の使い分け:

- Prompt A: 最も標準的なsleep ambient案。
- Prompt B: environmental tonesを強めた自然音寄り案。
- Prompt C: cinematic padsを強めた没入感重視案。
- Prompt D: minimal rhythmまたはpulseを少し入れたfocus兼用案。
- Prompt E: darkすぎないmysterious / dreamy寄りの差別化案。

## Expected Output

Codexから受け取りたい成果物はこの順番です。

1. Theme candidates
2. Mood candidates
3. Recommended theme / mood
4. Title candidates
5. Recommended title
6. Concept memo
7. Suno prompt candidates, 5 variants
8. Recommended Suno prompt
9. Thumbnail prompt
10. Thumbnail text
11. YouTube description
12. Checklist notes
13. Git update proposal

## Output Format

````markdown
## Theme Candidates

- {Theme A}: {日本語の狙い}
- {Theme B}: {日本語の狙い}
- {Theme C}: {日本語の狙い}

Recommended theme: {Theme A}
Recommended mood: Sleep, Calm, Peaceful

## Title Candidates

- {Title A} | Deep Sleep Ambient Music
- {Title B} | Healing Sleep Ambient
- {Title C} | Deep Sleep Ambient Music

Recommended: {Title A} | Deep Sleep Ambient Music

## Concept

日本語の制作メモ。

## Suno Prompt Candidates

### Prompt A - standard sleep ambient

Aim: {日本語の狙い}

```text
{prompt A}
```

### Prompt B - environmental tones

Aim: {日本語の狙い}

```text
{prompt B}
```

### Prompt C - cinematic pads

Aim: {日本語の狙い}

```text
{prompt C}
```

### Prompt D - focus compatible

Aim: {日本語の狙い}

```text
{prompt D}
```

### Prompt E - dreamy variation

Aim: {日本語の狙い}

```text
{prompt E}
```

Recommended Suno prompt: Prompt {A-E}

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
- テーマ未定の場合は、過去動画と被らないtheme候補を先に出す。
- しばらくはmoodをSleep中心にする。
- Suno promptは1日5種類まで作れる前提で、5案を提案する。
- タイトルは2〜3語の詩的な英語を優先する。
- 用途が伝わるように `| Deep Sleep Ambient Music` などを付ける。
- サムネイル本番画像は16:9。
- サムネイル文字は英語のみ。
- 人物、顔、ホラー感、強すぎるネオン、原色、情報過多を避ける。
- `NO VOCALS` をサムネイルで大きく主張しない。

## Manual Workflow

1. トリガー文でCodexに新規動画案を依頼する。
2. 提案されたtheme / mood候補から1つ採用する。
3. 提案されたtitle候補から1つ採用する。
4. 提案されたSuno prompt 5案を確認し、必要なら5種類すべて生成する。
5. 生成結果の良かった点、微妙だった点、次回改善点を `assets/music-prompts.md` に追記する。
6. thumbnail promptで16:9サムネイルを生成する。
7. `common/checklists/thumbnail-checklist.md` でサムネイルを確認する。
8. 採用サムネイルを `assets/references/` または今後作る `assets/thumbnails/` に保存する。
9. YouTube説明文を調整して公開または予約する。
10. `video-index.md` にVID、タイトル、テーマ、用途、進捗、参照画像パスを追記する。

## Example Request

```text
Driftaneの新規動画を作ります。
過去動画と被らないテーマを3〜5案出してください。
しばらくは睡眠向けを優先してください。

以下を提案してください:
- theme候補
- mood候補
- 採用推奨theme / mood
- title候補
- 採用推奨タイトル
- Suno prompt 5案
- thumbnail prompt
- thumbnail text
- YouTube description
- video-index.mdに追記する1行
- assets側に追記すべき改善メモ
```
