# ichiji

アプリ「一年の一字」の公開ページ（サポート、プライバシーポリシー、筆順のデータと権利）。

このフォルダの中身を、公開の GitHub のリポジトリ `kuwabaky/ichiji` のルートに置き、GitHub Pages で <https://kuwabaky.github.io/ichiji/> に出す。ビルドは要らない（静的な HTML と CSS だけ）。

**手で直さない。** 開発のリポジトリの `scripts/make-site.py` が作る（`style.css` だけは、手で書いたもの）。直すときは、台本を直して `python3 scripts/make-site.py` を流す。

## ページ

| ファイル | 中身 | 使う所 |
| --- | --- | --- |
| `index.html` | アプリの紹介と、各ページへの入口 | — |
| `privacy.html` | プライバシーポリシー | App Store Connect の「プライバシーポリシー URL」（`https://kuwabaky.github.io/ichiji/privacy.html`）、アプリの「このアプリについて」 |
| `support.html` | よくある質問と、問い合わせ先 | App Store Connect の「サポート URL」（`https://kuwabaky.github.io/ichiji/support.html`）、アプリの「このアプリについて」 |
| `strokes.html` | 筆順のデータの権利の表示と、写しの置き場 | アプリの権利の画面の「このデータの写しの置き場」（`https://kuwabaky.github.io/ichiji/strokes.html`） |
| `strokes.json`、`strokes-LICENSE.md` | アプリに入れるのと同じ筆順のデータ（KanjiVG から作った。CC BY-SA 3.0）と、権利の文 | 鍵のかからない形の写し（`https://kuwabaky.github.io/ichiji/strokes.json`） |
| `en/` | 英語の紹介、プライバシーポリシー、サポート | — |
| `style.css`、`icon.png` | 共通のスタイル、アイコン | — |

## 公開の前にすること

- HTML の中の `<!-- TODO -->`（連絡先のメール）を入れる。ほかのアプリの公開ページと同じ形（mailto のリンク）にする。
- 制定日を、公開する日にする（`scripts/make-site.py` の `DATE_JA`、`DATE_EN`）。
- 公開したら、`curl -fsSL https://kuwabaky.github.io/ichiji/strokes.json | shasum -a 256` が、開発のリポジトリの `content/2026/strokes.json` と同じになることを確かめる（`docs/release/testflight.md`）。
- 本文は、アプリの実際の動きと、`docs/release/privacy-policy.md`、アプリの中のデータの扱いの文に合わせてある。扱うデータが変わったら、同時に直す。
