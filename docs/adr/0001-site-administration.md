# ADR-0001: ユーザーサイトをサイト管理用リポジトリとして運用する

## ステータス

承認済み

## 日付

2026-10-06

## コンテキスト

GitHub Pagesのユーザーサイト `junpeimay-wq.github.io` のドメイン直下に `robots.txt` を配置する必要がある。ゲームサイトはプロジェクトサイト `junpeimay-wq.github.io/games/` として別リポジトリで公開しており、プロジェクトサイトのファイルだけではドメイン直下のrobots.txtを提供できない。また、Google Search Consoleにサイトの所有権を確認させるため、Googleが発行した確認用HTMLファイルをドメイン直下から配信する必要がある。

## 決定

- `junpeimay-wq.github.io` リポジトリを、GitHub Pagesユーザーサイトの公開ルートとサイト管理設定を管理する専用リポジトリとして運用する。
- ドメイン直下の `robots.txt` と、ゲームサイトへの案内に必要な最小限のルートページをこのリポジトリで管理する。
- Google Search Consoleで発行された所有権確認用HTMLファイルを、ファイル名・内容を変更せずドメイン直下に配置して公開する。これはGoogleにサイトの所有権を確認させるためのものであり、ゲームの機能やサイト利用者向けコンテンツではない。
- ゲーム本体やゲームサイト固有のコンテンツは `games` リポジトリで管理し、このリポジトリに複製しない。
- ルートの `README.md` と `docs/` 以下のADRは、リポジトリの説明・運用判断を記録する内部資料とする。Jekyllの `_config.yml` でGitHub Pagesの公開対象から除外する。
- この決定は、READMEとADRをGitHub PagesのWebサイトに掲載しないことを意味する。リポジトリのアクセス権は別途管理し、公開リポジトリ上のソース自体は閲覧可能である。

## 理由

- ユーザーサイトのドメイン直下とプロジェクトサイトの公開ルートを正しく分離できる。
- ルートのクロール設定を一元管理しつつ、ゲームの実装とリリースは既存のゲームリポジトリに維持できる。
- Google Search Consoleの所有権確認ファイルをドメイン直下から配信することで、Googleの確認手順を満たせる。
- 運用説明と設計判断を記録しながら、それらを公開サイトのコンテンツに混在させない。

## トレードオフ

- GitHub PagesのJekyll設定を維持し、READMEやADRが公開対象に含まれないことを確認する必要がある。
- 公開リポジトリである限り、Pagesから除外したMarkdownファイルもGitHubのリポジトリ画面やraw URLでは閲覧できる。機密情報や非公開にすべき情報は格納しない。

## 参考

- [GitHub Pages: Creating a GitHub Pages site](https://docs.github.com/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [GitHub Pages: Jekyll configuration options](https://jekyllrb.com/docs/configuration/)
- [Google Search Console: Verify your site ownership](https://support.google.com/webmasters/answer/9008080)
