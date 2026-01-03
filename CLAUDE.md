# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

業務用工場向け工具の製品サイト。静的HTML/CSSのみで構成。

**コンセプト**: 「売りに行かない。探している人だけを受け止める」

## 本番URL

https://omooooori.github.io/rosenhouse/

## ローカル確認

```bash
python -m http.server 8000
# or
npx serve
```

## サイト構成

| ページ | ファイル | 内容 |
|--------|----------|------|
| TOP | `index.html` | 製品説明メイン |
| 会社概要 | `about.html` | 会社情報 |
| 保証 | `support/warranty.html` | 保証・免責 |
| 問い合わせ | `support/contact.html` | Googleフォーム埋め込み |

## 設計方針

- 静的HTMLのみ（CMS不使用）
- 将来の製品追加に対応できる構造
- 運用コスト実質ゼロ（GitHub Pages無料枠）
- やらないこと: 広告、SEOブログ、SNS、EC決済、WordPress

## 製品追加時

1. `index.html` に製品セクションを追加
2. `docs/` に技術仕様PDFを配置
3. Googleフォームのプルダウンに製品を追加
