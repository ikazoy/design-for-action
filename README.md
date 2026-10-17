# Design for Action

ユーザーの状況・目的・メンタルモデルから、理解して操作できるUIを設計するエージェントスキルです。

**説明文を、分かりにくいUIの埋め合わせに使わない。** まずラベル、配置、まとまり、操作の流れを整え、文章は判断・操作・復旧に必要な不足を補うために使います。

## インストール

[Skills CLI](https://github.com/vercel-labs/skills) を使います。現在のCLIが要求するNode.jsは22.20.0以上です。

```sh
npx skills@latest add ikazoy/design-for-action --skill design-for-action --global --agent claude-code codex --yes
```

Claude CodeとCodexの両方へ、ユーザー共通のスキルとしてインストールします。対象を一方だけにする場合は `--agent claude-code` または `--agent codex` を指定してください。

更新は次のコマンドで行えます。

```sh
npx skills@latest update design-for-action --global --yes
```

## 使い方

Claude Code:

```text
/design-for-action この画面を、ユーザーの状況・目的・メンタルモデルから見直して
```

Codex:

```text
$design-for-action この画面を、ユーザーの状況・目的・メンタルモデルから見直して
```

新しいセッションで利用してください。依頼に応じた自動選択も対象にしています。

アプリの画面、フォーム、設定、ダッシュボード、空の状態、UI文言の改善・レビューに使います。広告文やブランド表現だけの作業は対象外です。

## 方針

- 利用状況、片づけたい用事、操作後に予想する結果を起点にする。
- 情報の強弱、用語、配置、操作を、その人の仕事に合わせる。
- 画面ですでに伝わる説明、操作を代用する案内、実装事情、補足欄を埋めるだけの文章を抑える。
- 料金、削除、外部通知、権限など、判断を変える条件は残す。
- 各説明文を消したときに起きる具体的な問題を確かめ、役割のない説明は削除する。

本文は [SKILL.md](skills/design-for-action/SKILL.md)、判断例は [examples.md](skills/design-for-action/references/examples.md) にあります。

## 参照・着想元のスキル

以下の4つを参照し、このスキルの目的に合わせて構成と文章を新たにまとめました。参照元の全文やコードは同梱していません。

| 参照元 | 取り入れた要素 | 原典のライセンス |
|---|---|---|
| [artouc / stop-describing-ui](https://github.com/artouc/stop-describing-ui/blob/251a859f6e40645030e1ae69fa4b501c851eac9c/skills/stop-describing-ui/SKILL.md) | 説明過多の抑制、具体的な動詞、重複の整理、案内を実際の操作へ置き換える視点 | [MIT](https://github.com/artouc/stop-describing-ui/blob/251a859f6e40645030e1ae69fa4b501c851eac9c/LICENSE) |
| [Microsoft / VS Code design-philosophy](https://github.com/microsoft/vscode/blob/59ef8a091da1c9d6745792866c163745ee6fc29b/.github/skills/design-philosophy/SKILL.md) | 価値・判断原則・具体的な変更をつなぐ構成、情報の強弱、意味のある一貫性 | [MIT](https://github.com/microsoft/vscode/blob/59ef8a091da1c9d6745792866c163745ee6fc29b/LICENSE.txt) |
| [Paul Bakaus / Impeccable — clarify](https://github.com/pbakaus/impeccable/blob/5bf0a069dc857e1b5f4b090e004d9d5b231416ca/.agents/skills/impeccable/reference/clarify.md) | 文脈に合うメッセージ階層、状態と次の行動、復旧を支える言葉 | [Apache-2.0](https://github.com/pbakaus/impeccable/blob/5bf0a069dc857e1b5f4b090e004d9d5b231416ca/LICENSE) |
| [Dammyjay93 / interface-design](https://github.com/Dammyjay93/interface-design/blob/2f9be3206855bcb2d1d0af262c8bae25cba6658d/.claude/skills/interface-design/SKILL.md) | 誰がどんな場面で何をするかを先に捉え、設計意図を構造と実装へ反映する視点 | [MIT](https://github.com/Dammyjay93/interface-design/blob/2f9be3206855bcb2d1d0af262c8bae25cba6658d/LICENSE) |

統合時の判断と引き継がなかった規定は [sources.md](skills/design-for-action/references/sources.md) に記載しています。参照元のインストールは不要です。

## 検証範囲

スキルの形式と参照リンクを検証し、作成時に4つの利用場面で定性的な机上確認を行いました。実ユーザー調査や他スキルとの比較による有効性の検証は行っていません。

## ライセンス

このリポジトリの独自の記述は [MIT License](LICENSE) で公開します。参照元は、それぞれのライセンスに従います。
