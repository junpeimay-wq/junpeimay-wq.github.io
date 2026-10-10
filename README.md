# junpeimay-wq.github.io

このリポジトリは、`junpeimay-wq.github.io` のGitHub Pages公開設定を管理するサイト管理用リポジトリです。公開ドメイン直下のファイルを管理し、現在は次の用途に限定しています。

- `sitemap.xml` でホストルートからのサイトマップを提供する
- `robots.txt` でクロール方針とサイトマップ（`https://junpeimay-wq.github.io/sitemap.xml`）を案内する
- `index.html` から `games` サイトへ案内する

ゲーム本体は [`junpeimay-wq/games`](https://github.com/junpeimay-wq/games) で管理します。このリポジトリにはゲーム本体を複製しません。

## 内部ドキュメント

設計判断は [`docs/adr/`](docs/adr/) にArchitecture Decision Record（ADR）として記録します。READMEとADRはGitHub Pagesから公開せず、リポジトリ内の運用資料として保持します。
