# ADR-0002: ホストルートへの sitemap.xml 配置と robots.txt の更新

## ステータス

承認済み

## 日付

2026-10-10

## コンテキスト

これまで `sitemap.xml` は `games` リポジトリ（`junpeimay-wq.github.io/games/sitemap.xml`）に配置されていた。Google Search Console や各種検索エンジンがホストルート（`junpeimay-wq.github.io/sitemap.xml`）でのサイトマップ読み込みを優先するケースに対応するため、ユーザーサイト `junpeimay-wq.github.io` のルートにサイトマップを移動・配置する必要が生じた。

## 決定

- `junpeimay-wq.github.io` リポジトリのルートに `sitemap.xml` を配置する。
- サイトマップには `https://junpeimay-wq.github.io/games/` 配下の公開ゲームおよびランキングページのURLを網羅する。
- `robots.txt` の `Sitemap:` 記述を `https://junpeimay-wq.github.io/sitemap.xml` へ変更する。

## 理由

- ホストルートに `sitemap.xml` を直接配置することで、検索エンジンによるクロールおよび Search Console でのサイトマップ認識の失敗を防ぐ。
- ルートの `robots.txt` と `sitemap.xml` を同一のユーザーサイトリポジトリで一元管理できる。

## トレードオフ

- 今後 `games` リポジトリ側で新しいゲームや公開ページを追加・変更した際には、`junpeimay-wq.github.io` リポジトリ側の `sitemap.xml` も合わせて更新する必要がある。
