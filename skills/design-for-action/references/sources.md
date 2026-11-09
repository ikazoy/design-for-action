# 参照元と統合方針

参照元の考え方を比較し、このスキルの目的に合わせて日本語で新たに記述した。原文の全文やコードは同梱していない。
確認日：2026-10-16（ウォークスルーの参照元3件は2026-11-09）。リンクは確認したコミットに固定している。

| 参照元 | 取り入れた考え方 | このスキルでの扱い |
|---|---|---|
| [artouc/stop-describing-ui](https://github.com/artouc/stop-describing-ui/blob/251a859f6e40645030e1ae69fa4b501c851eac9c/skills/stop-describing-ui/SKILL.md) | 具体的な動作と対象を示すラベル、重複する説明の整理、案内を操作に置き換える。 | 説明による埋め合わせを避ける原則、4つの禁止事項、各説明文の削除レビューを本文に置く。補足を残す基準は「その人の判断・予測・復旧を助けるか」。内部処理や複数の影響も必要なら伝える。記号やアイコンの一律指定は引き継がない。 |
| [microsoft/vscode](https://github.com/microsoft/vscode/blob/59ef8a091da1c9d6745792866c163745ee6fc29b/.github/skills/design-philosophy/SKILL.md) | 価値・原則・具体的な変更をつなぐ構成、情報の強弱、意味のある一貫性。 | 原則に判断の問いを添え、状況によるトレードオフを扱う。VS Code固有のトークン、寸法、配色の規定は引き継がない。 |
| [pbakaus/impeccable](https://github.com/pbakaus/impeccable/blob/5bf0a069dc857e1b5f4b090e004d9d5b231416ca/.agents/skills/impeccable/reference/clarify.md) | clarifyのメッセージ階層、文脈に合う言葉、状態と復旧の伝達。 | 文言単体より前後の操作を重視。ユーザーの知識、心理、メンタルモデルに合わせる。ランチャーや他のコマンドへの依存は持たない。 |
| [Dammyjay93/interface-design](https://github.com/Dammyjay93/interface-design/blob/2f9be3206855bcb2d1d0af262c8bae25cba6658d/.claude/skills/interface-design/SKILL.md) | 誰がどんな場面で何をするかから設計し、意図を構造と実装に反映する。 | その人が予想する対象・順序・結果を具体化する。独自の見た目、配色探索、コンポーネントごとの定型宣言は必須にしない。 |
| [mastepanoski/cognitive-walkthrough](https://github.com/mastepanoski/claude-skills/blob/0b50d6eb5f3a66b781492604723d65524ee920e2/skills/cognitive-walkthrough/SKILL.md) | タスクを操作に分け、各操作を4つの問いで評価する。根拠のない数値を作らない。 | 4つの問いを、実画面の操作と予測のズレの記録に結び付ける。所要時間の目安と報告テンプレートは引き継がない。 |
| [jezweb/ux-audit](https://github.com/jezweb/claude-skills/blob/57e060f4a910f4792320bb1ad10e11183adb97dd/plugins/dev-tools/skills/ux-audit/SKILL.md) | 実画面を操作した記録を求める。検証の前に人物を固定する。 | 操作の記録と人物の固定だけを使う。シナリオ一式、自動判定、見た目の監査は引き継がない。 |
| [Owl-Listener/synthetic-user-testing](https://github.com/Owl-Listener/designpowers/blob/b7cca247ea3d17a0f06c1f0cc2edfbe0cf6a37f3/skills/synthetic-user-testing/SKILL.md) | 状況・用事・人物・成功条件で場面を書き、操作ごとに見えるものと結果を記録する。 | 前提の項目と記録の発想を使う。専用パイプラインへの依存と固定の人物像は引き継がない。 |

## 運用

- 本文は使う場面と判断原則を扱い、具体例と検証の手順は必要なときに読む。
- 参照元スキルは背景資料であり、実行時の依存関係にはしない。
- 説明過多を防ぐ少数の禁止事項と、状況・目的・予測から判断する原則を組み合わせる。個別事例のたびに禁止事項を増やすより、既存の原則で修正理由を説明する。
- 既存のスキルは自動で無効化・置換しない。この方針を指定するときは `$design-for-action` を明示する。複数スキルの方針がぶつかる場合は、ユーザーが今回選んだ方針を優先する。
- 特定製品の事情を恒久ルールへ移す前に、複数の場面でも役立つ判断基準かを確かめる。
