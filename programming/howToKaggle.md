---
title : How to Kaggle
category : Python
author : Makoto Yaugchi
---

# How to Kaggle
- Kaggle とは世界中のデータサイエンス・機械学習に携わる人が参加するコミュニティーサイト
- サイト上にコーディング環境があり、Python/R言語でのデータ分析および機械学習ができる
- 企業や政府などの組織がコンペを開催しており、高い分析モデルに賞金が与えられるコンペもある

[TOC]

## Kaggle Titanic about Reference Site
- [Kaggle](https://www.kaggle.com/code/plasticgrammer/kaggle-titanic)
- [Qiita](https://qiita.com/jun40vn/items/d8a1f71fae680589e05c)
- [codexa](https://www.codexa.net/kaggle-titanic-beginner/)

## Python 使用ライブラリ
- Numpy
- Pandas
- matplotlib
- Seaborn
- scikit-learn

## Kaggel のキーワード
- Competition : コンペ
- Dataset : 公開されているデータ
- Notebook : ソースファイル
- Leadersboard : スコアランキング
- Public Leaderboard : 公開スコア
- Private Leaderboard : 非公開スコア

## Titanic コンペに参加してみる
- 概要を確認
- Notebook を作成
 
## 機械学習の流れ
- データ読み込み
- データ分析
- 前処理 <- 精度に大きく影響
- モデル作成、学習、予測 <- 精度に大きく影響
- 評価

## 予測精度向上の取り組み
- 精度の検証
- ホールド検証
    - 交差検証
    - まずやってみること
- その他
    - 特徴量の可視化
    - 一人旅かどうかが生存率に影響しているのか？（SibSp＋Parch≦1）
    - 名前やチケット番号から情報を抜き出せないか考えてみる
    - KFoldクラスを使用して、交差検証をする
    - 別の人が作成したNotebookを見て、良いアイデアを見つける

## さいごに
- 機械学習は、ライブラリの使い方から始まり、統計や数学など、幅広い知識を求められている
- その全てを基礎から学ぼうとすると大変なので、統計や数学については「必要を感じるまで学ばない」ことをオススメする
- Kaggleでコンペ入賞を目指すぐらいのモチベーションになるまでは、逆に「どこまで勉強せずにやれるか」ぐらいに考えるとベター

## 追記

- カラムの意味

|カラム名|和訳|
|:--:|:-- |
|PassengerId|乗客のID|
|Survived| 生存=1, 死亡=0 (trainのみ) |
|Pclass| 階級|
|Name| 名前|
|Sex| 性別|
|Age| 年齢|
|SibSp| 兄弟(姉妹)、夫(妻)の数（自分を除く）|
|Parch| 両親、子供の数|
|Ticket| チケットナンバー|
|Fare| 乗船料金|
|Cabin| キャビン番号|
|Embarked| 乗車場|