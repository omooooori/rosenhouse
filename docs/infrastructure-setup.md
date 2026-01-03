# インフラ設定ログ

## 現在の状態

| 項目 | 状態 |
|------|------|
| 本番 URL | https://rosenhouse.jp/ （DNS設定待ち） |
| Cloudflare Pages | https://rosenhouse.pages.dev/ （稼働中） |
| GitHub Pages | https://omooooori.github.io/rosenhouse/ |
| ドメイン登録 | お名前.com |
| DNS管理 | Cloudflare（移行中） |
| ホスティング | Cloudflare Pages |

---

## 2025-01-03: SEO対策

### 実施内容

1. **sitemap.xml 作成**
   - 全4ページを登録
   - changefreq, priority 設定済み

2. **robots.txt 作成**
   - sitemap.xml への参照を追加

3. **構造化データ（JSON-LD）追加** - index.html
   - Organization スキーマ（会社情報、住所）
   - WebSite スキーマ

4. **canonical URL 追加** - 全ページ

5. **OGP タグ追加** - 全ページ
   - og:title, og:description, og:type, og:url, og:image, og:site_name, og:locale
   - twitter:card

6. **ロゴ alt テキスト修正** - 全ページ
   - 空 → 「ローゼンハウス ロゴ」

---

## 2025-01-03: リポジトリ名修正

### 実施内容

- GitHub リポジトリ名のタイポ修正
  - `rosenhaus` → `rosenhouse`
- 全ファイル内の URL を更新

---

## 2025-01-03: ドメイン取得・Cloudflare Pages 移行

### 実施内容

1. **ドメイン取得**
   - `rosenhouse.jp` をお名前.com で取得

2. **Cloudflare Pages デプロイ**
   - GitHub リポジトリ `omooooori/rosenhouse` を連携
   - ビルド設定: 静的HTML（ビルドコマンドなし）
   - デプロイ URL: https://rosenhouse.pages.dev/

3. **Cloudflare DNS 設定準備**
   - Cloudflare に `rosenhouse.jp` をサイトとして追加
   - 不要な DNS レコードを削除（お名前.comからインポートされた古いレコード）
   - Cloudflare ネームサーバーを確認:
     - `angela.ns.cloudflare.com`
     - `clyde.ns.cloudflare.com`

### 保留中

- **お名前.com でネームサーバー変更ができない**
  - 原因: ドメインプロテクションが有効
  - 管理画面から解除できない状態
  - 対応: お名前.com サポートに解除依頼中

---

## 次のステップ

1. [ ] お名前.com でドメインプロテクション解除
2. [ ] ネームサーバーを Cloudflare に変更
   ```
   angela.ns.cloudflare.com
   clyde.ns.cloudflare.com
   ```
3. [ ] DNS 反映を待つ（数分〜数時間）
4. [ ] Cloudflare Pages で `rosenhouse.jp` をカスタムドメインに追加
5. [ ] HTTPS 有効化を確認
6. [ ] GitHub Pages の CNAME ファイル削除
7. [ ] Google Search Console に登録
   - サイトマップ URL: https://rosenhouse.jp/sitemap.xml

---

## 参考: DNS 設定（Cloudflare Pages 連携後に自動設定）

カスタムドメイン追加時に Cloudflare が自動で以下を設定：

| TYPE | Name | Content |
|------|------|---------|
| CNAME | rosenhouse.jp | rosenhouse.pages.dev |
| CNAME | www | rosenhouse.pages.dev |
