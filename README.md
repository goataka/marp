# marp

MarpでMarkdownからPDFプレゼンテーションを生成するリポジトリです。

## 概要

このリポジトリでは、[Marp](https://marp.app/)を使用してMarkdownファイルからPDFプレゼンテーションを生成できます。GitHub Actionsを使った手動トリガーによるPDF生成をサポートしています。

## 使い方

### 手動でPDFを生成する

1. GitHubリポジトリの「Actions」タブに移動
2. 左サイドバーから「Manual PDF Generation」を選択
3. 「Run workflow」ボタンをクリック
4. 以下のパラメータを指定：
   - **ブランチ名**: PDF生成に使用するブランチ（例: `main`）
   - **Markdownファイルのパス**: 変換したいMarkdownファイル（例: `example.md`）
5. 「Run workflow」をクリックして実行
6. ワークフロー実行完了後、「Artifacts」セクションから生成されたPDFをダウンロード

### Markdownファイルの作成

Marp形式のMarkdownファイルには、フロントマターで`marp: true`を指定する必要があります：

```markdown
---
marp: true
theme: japanese
paginate: true
---

# タイトルスライド

最初のスライドの内容

---

## 次のスライド

2枚目のスライドの内容
```

### 日本語フォントについて

PDFに日本語を正しく表示するため、`japanese`テーマを使用することを推奨します。このテーマは日本語フォント（Noto Sans CJK JP）を明示的に指定しています。

デフォルトテーマを使用したい場合でも、ワークフローで日本語フォントがインストールされるため、日本語は正しく表示されます。


## サンプルファイル

- `example.md`: Marpプレゼンテーションのサンプルファイル

## 機能

- ✅ ブランチを指定してPDF生成
- ✅ 任意のMarkdownファイルを指定してPDF生成
- ✅ 生成されたPDFを自動的にArtifactsとして保存（30日間保持）
- ✅ 日本語対応

## 参考リンク

- [Marp公式サイト](https://marp.app/)
- [Marp CLI](https://github.com/marp-team/marp-cli)
- [Marp記法ガイド](https://marpit.marp.app/markdown)