# ローゼンハウス 製品サイト

業務用工場向け工具の製品サイト。

## URL

- **本番**: https://omooooori.github.io/rosenhouse/

## 構成

```
/
├── index.html          # TOPページ（製品説明）
├── about.html          # 会社概要
├── support/
│   ├── warranty.html   # 保証・免責
│   └── contact.html    # お問い合わせ
├── docs/               # 技術仕様PDF
└── assets/
    ├── css/
    └── images/
```

## 技術スタック

- 静的HTML/CSS
- ホスティング: GitHub Pages（将来的にCloudflare Pagesへ移行予定）

## ローカル確認

```bash
# Python
python -m http.server 8000

# Node.js
npx serve
```

## TODO

- [ ] Googleフォーム作成・埋め込み
- [ ] 製品名・詳細情報の記載
- [ ] 技術仕様PDF追加
- [ ] 会社情報の記載
- [ ] 独自ドメイン設定
