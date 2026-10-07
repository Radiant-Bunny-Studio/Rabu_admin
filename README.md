# Rabu — radiantbunnystudio.com

Radiant Bunny Studio株式会社のコーポレートサイト。GitHub Pagesで公開する静的サイト（ビルド不要）。

## 構成
- `index.html` トップ（ニュース最新3件・スタジオ紹介・事業内容・会社概要・お問い合わせ）
- `news.html` ニュース一覧（すべての記事）
- `career.html` 採用情報（募集職種・応募方法）
- `privacy.html` プライバシーポリシー（App Storeのプライバシーポリシー URL）
- `support.html` サポート・お問い合わせ（App Storeのサポート URL）
- `404.html` / `CNAME` / `.nojekyll`
- `assets/css/style.css` 共通スタイル、`assets/img/` ロゴ類

ヘッダー・フッターは各HTMLに直接書いてある。メニューを変えるときは6ファイルすべて直す。サポートはヘッダーのメニューには出さず、フッターからだけリンクする（App Store のサポート URL として残す）。

ニュースを足すときは `news.html` の先頭に1件足し、`index.html` の `#news` も最新3件に入れ替える。

## 公開手順
1. Organization（radiant-bunny-studio）配下のリポジトリ `Rabu_admin` に、このフォルダの中身を `main` にpush
2. Settings → Pages → Source: Deploy from a branch / `main` / `/ (root)`
3. Visibility を **Public** にする（Enterprise Cloudでは要確認）
4. Custom domain に `radiantbunnystudio.com` → Enforce HTTPS をON
5. Organization Settings → Pages → Verified domains でドメインを検証

## DNS（Squarespace Domains側）
MXなどメール系のレコードには触らない。追加するのは以下だけ。

| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | <org名>.github.io |

Squarespaceのデフォルト（パーキング/Squarespaceサイト向け）のA・CNAMEレコードが残っていたら削除する。
