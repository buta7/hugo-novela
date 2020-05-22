# README

## セットアップ

サイト作成

```shell
hugo new site hugo-novela
```

レポジトリ初期化

```shell
cd hugo-novela
git init
echo '*.bak' >> .gitignore
echo '*~' >> .gitignore
echo '*.orig' >> .gitignore
echo 'public' >> .gitignore
echo '.env' >> .gitignore
```

テーマ設定

```shell
cd themes
git submodule add git@github.com:forestryio/hugo-theme-novela.git
```

サイト設定

```shell
cd ..
cp -pr themes/hugo-theme-novela/exampleSite/{content,config.yaml} .
```

config.toml

```toml
baseURL = "https://example.com"
languageCode = "ja"
title = "Hugo Novela"
theme = "hugo-theme-novela"
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

起動確認(http://localhost:1313)

```shell
cp /path/to/someplace/Makefile .
make run
```

Githubレポジトリ作成後

```shell
git remote add origin git@github.com:higebobo/hugo-novela.git
git add .
git commit -m 'init'
git push -u origin master
```

## Github Actionsの利用

* .github/workflows/gh-pages.yamlを作成
    * ソースはmasterブランチ
    * 出力はpublicフォルダの内容をgh-pagesブランチ
        * Github>Settings>Gighub Pages>Source>gh-pages branch

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:higebobo/hugo-novela.git higebobo-novela
cd higebobo-novela
git submodule update --init --recursive
```

## 使い方

### 投稿

新規投稿

```shell
hugo new posts/hello.md
content/posts/hello.md created
```

編集

```shell
vi content/posts/hello.md
```

## Link

* [Hugo Theme Novela \| Hugo Themes](https://themes.gohugo.io/hugo-theme-novela/)
