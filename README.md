# ローゼンハウス 製品サイト

業務用工場向け工具の製品サイト。

## URL

https://rosenhouse.jp/

## 構成

```
/
├── index.html          # TOPページ（製品説明）
├── about.html          # 会社概要
├── support/
│   ├── warranty.html   # 保証・免責
│   └── contact.html    # お問い合わせ（Google フォーム）
├── docs/               # 技術仕様PDF
├── assets/
│   ├── css/
│   └── images/
├── sitemap.xml
└── robots.txt
```

## 技術スタック

- 静的HTML/CSS
- ホスティング: Cloudflare Pages
- DNS: Cloudflare
- ドメイン: お名前.com

## ローカル確認

```bash
python -m http.server 8000
# or
npx serve
```
