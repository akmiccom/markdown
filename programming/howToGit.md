---
Title : Git Cheat Sheet
Category : Programming
Author : Makoto Yaugchi
---

# Git Cheat Sheet

[TOC]

## Git とは
- バージョン管理システム
- 簡単に履歴をたどることができるツール

## 重要な機能 branch と marge

フォルダとファイルの作成
```Bash
mkdir testFolder
cd testFolder
echo Hello > testFile.md
```

Git の初期化～コミット
```Bash
git init  # 初期化
git add testFile.md  # ステージングというやつ
git commit -m "first commit"  # 名前を付けてコミット 
git log --oneline  # logの確認
# 4ee5e15 (HEAD -> master) first commit
```

Git の branch の操作
```Bash
git branch  # ブランチ一覧(*が今いるブランチ)
# * master
git branch develop
git branch  # ブランチ一覧(*が今いるブランチ)
#   develop
# * master
git checkout develop  # ブランチの切り替え
# Switched to branch 'develop'
git branch  # ブランチ一覧(*が今いるブランチ)
# * develop
#   master
```

branch の使い分け操作
- 二つのブランチにあえて同じような操作を行っている
```Bash
git checkout master
git add .
git commit -m 'master.txt を追加'
git add .
git commit -m 'README.md に「master」と追記'
git log --oneline
# 8949425 (HEAD -> master) README.md に「master」と追記
# de0e1e3 master.txt を追加
# 365e518 first commit
```

```Bash
git checkout develop
git add .
git commit -m 'develop.txt を追加'
git add .
git commit -m 'README.md に「develop」と追記'
git log --oneline
# 4f390bd (HEAD -> develop) README.md に「develop」と追記
# a15a08e develop.txt を追加
# 365e518 first commit
```

マージ は親に checkout して実行
- marge する branch   → **theirs** イメージは子
- marge される branch  → **ours** イメージは親

```Bash
git branch  # checkout を確認
#   develop
# * master
git merge develop
# Auto-merging README.md
# CONFLICT (content): Merge conflict in README.md
# Automatic merge failed; fix conflicts and then commit the result.
```

今回は CONFLICT が起き、自動マージは失敗するようにしていた
```Bash
git status
# On branch master
# -- omission --
# Unmerged paths:
#   (use "git add <file>..." to mark resolution)
#         both modified:   README.md
```

このような場合は対称ファイルに対し手動で修正を行うことが望ましい
vscode ならば比較しながら merge ができる
```Bash
git merge-base master develop
# 365e5183d82091e4ee1b1c3304c0814fa67b710e
# first commit のハッシュにより分岐点を確認できる
git diff 365e5183d82091e4ee1b1c3304c0814fa67b710e develop README.md
git diff 365e5183d82091e4ee1b1c3304c0814fa67b710e master README.md
```

## 

