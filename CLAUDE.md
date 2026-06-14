# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## このリポジトリの性質

GNU Emacs 用アイコン集 (Emacs Icon Collections)。**コードリポジトリではなくアセットリポジトリ**であり、ビルド/lint/テストの仕組みは存在しない。作者 (nanasess) が作成したこのアイコンは GNU Emacs 23 / 24 の公式アイコンとして採用されている。

Emacs の `E` と `M` をモチーフに GNU horn のイメージを合致させたデザインで、Andrew Zhilin 氏による Emacs22 アイコンのイメージを踏襲している。付属のペンはパーカー51 (万年筆) がモチーフ。

ライセンスは全同梱イメージに対して **GPL** (`gpl-3.0.txt` / `LICENSE.txt`)。

## アセット構成とソース・オブ・トゥルース

2 種類のアイコンセット (`app_icons/` = アプリケーションアイコン、`document_icons/` = ドキュメントアイコン) があり、それぞれ同一デザインを複数フォーマットで保持する。

**編集の起点は必ずベクタ原本**。派生ラスタ/プラットフォーム形式を直接編集しない:

- `ai/*.ai` — Illustrator 10 で作成されたベース画像 (最上流の原本)
- `svg/*.svg` — SVG 版
- `psd/*.psd` — Photoshop 版 (`emacs_icon_no_pen.psd` はペンを省いた派生)

これらから書き出される派生物:

- `png/` — 16/24/32/48/128/256/512px。一部は `_8bit` / `_24bit` のビット深度違いを持つ
- `xpm/` — 16/24/32/48px (Emacs が読み込む形式)
- `ico/emacs.ico` — Windows アイコン
- `icns/` — macOS アイコン

## 作業上の注意

- **アイコン更新時は全フォーマットの一貫性を保つ**: デザイン変更は原本 (ai/svg/psd) に加えた上で、png・xpm・ico・icns の全サイズ/全形式を再書き出しする。コミット履歴 (`updated Windows Icon`, `updated 32px and 16px icons`, `updated SVG Image` 等) もフォーマット単位での更新を示す。1 形式だけ更新して他を取り残さない。
- バイナリアセット (png/psd/ai/ico/icns/pptx) が中心のため、diff はテキストとして読めない。変更内容は `git status` とファイル名から判断する。
- `git add -A` を使わず、更新したアセットを個別に add する (ユーザー共通ルール)。
- ルート直下の `kansaiemacs-100925014703-phpapp01.pptx` は Kansai Emacs 発表「Emacs アイコンがコミットされるまで」のスライド資料 (README の See Also と対応)。一方 `*.pptx:Zone.Identifier` は Windows のダウンロードマーク (WSL が生成するメタデータ) であり、コミット対象に含めない。

## 参考

- README.md にデザインの意図、同梱ファイル一覧、謝辞がまとまっている。
- 関連スライド: 「Emacs アイコンがコミットされるまで」(slideshare.net/nanasess/emacs-5282932)
