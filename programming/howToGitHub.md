---
Title : How to Github
Category : Programming
Author : Makoto Yaugchi
---

# How To GitHub

[TOC]

## Visual Studio Code による Github の使い方
VSCodeなら、コーディングと Git の操作が可能ですので、使い方を覚えておくと非常に有効であると考えられます。
手順として、いくつかあるのですが、一番簡単で汎用性(繰り返しやることになる作業)が以下の方法ではないかと考えました。

初期設定
1. Github でリモートリポジトリを作成
2. vscode でクローンを作成
3. vscode でクローンからブランチを作成
4. vscode で作業する

作業完了時
1. vscode でプッシュする
2. Github でマージをする

これであれば GIT のコマンドを内必要がないので最初のうちは簡単ではないかと思います。もしかしたら remote が必要であったり、proxy の設定が必要であったりするかもしれません。それらは追記で対応していきます。

## 
































## Overview

- 簡単にGitHubの使い方をまとめておく
- proxyの設定が必要となる

## GutHubでリモートリポジトリを作成

- GitHubにログイン
- リポートリポジトリ作成

## Gitの設定

- ローカルリポジトリ作成
- ローカルリポジトリにファイルをaddする
- ローカルリポジトリにcommitする
- ローカルリポジトリからリモートリポジトリにremoteする
- リポートリポジトリにファイルをpushする

## command

```PowerShell
# create a new repository on the command line

git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/<userID>/<repositoryName>.git
git push -u origin
# 2回目から
git push
```

```PowerShell
# push an existing repository from the command line

git remote add origin https://github.com/<userID>/<repositoryName>.git
git branch -M main
git push -u origin
```

## 上の方法でうまくいかないときの手順

1. githubで新しいRepositoryを作成する
2. クローンを作成したいフォルダで以下のコマンドを実行する
    1. git clone https://github.com/<userID>/<repositoryName>.git
3. Repositry の名前でフォルダとファイル、gitが作成される

