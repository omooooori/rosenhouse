# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

業務用工場向け工具の製品サイト。静的HTML/CSSのみで構成。

**コンセプト**: 「売りに行かない。探している人だけを受け止める」

## 本番URL

https://rosenhouse.jp/

## インフラ構成

| 項目 | 設定 |
|------|------|
| ホスティング | Cloudflare Pages |
| ドメイン | rosenhouse.jp（お名前.com で取得） |
| DNS | Cloudflare |
| フォーム | Google フォーム（埋め込み） |

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
| 問い合わせ | `support/contact.html` | Google フォーム埋め込み |

## SEO 対策（実施済み）

- sitemap.xml
- robots.txt
- 構造化データ（JSON-LD）: Organization, WebSite
- OGP タグ
- canonical URL

## 設計方針

- 静的HTMLのみ（CMS不使用）
- 将来の製品追加に対応できる構造
- 運用コスト実質ゼロ
- やらないこと: 広告、SEOブログ、SNS、EC決済、WordPress

## 製品追加時

1. `index.html` に製品セクションを追加
2. `docs/` に技術仕様PDFを配置
3. Google フォームのプルダウンに製品を追加
