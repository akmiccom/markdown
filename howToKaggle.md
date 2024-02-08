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

### ライブラリインポート


```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### データの読み込み


```python
train = pd.read_csv('../csv/train.csv')
test = pd.read_csv('../csv/test.csv')
print(train.shape)
print(test.shape)
```

    (891, 12)
    (418, 11)
    

### データ分析の結果
- 機械学習では分析対象を特徴量(feature)と呼ぶ

- train の列一覧
    - 'PassengerId', 'Survived', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp', 'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked'
- test の列一覧
    - 'PassengerId', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp', 'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked'
- データ数
    - train = (891, 12)
    - test = (418, 11)
- 欠損値
    - train
        - Age            177
        - Cabin          687
        - Embarked         2
    - test
        - Age             86
        - Fare             1
        - Cabin          327
- 統計量

### データの確認


```python
print(f'Data size = {train.shape}')
train.head(3)
```

    Data size = (891, 12)
    

```python
train.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 891 entries, 0 to 890
    Data columns (total 12 columns):
     #   Column       Non-Null Count  Dtype  
    ---  ------       --------------  -----  
     0   PassengerId  891 non-null    int64  
     1   Survived     891 non-null    int64  
     2   Pclass       891 non-null    int64  
     3   Name         891 non-null    object 
     4   Sex          891 non-null    object 
     5   Age          714 non-null    float64
     6   SibSp        891 non-null    int64  
     7   Parch        891 non-null    int64  
     8   Ticket       891 non-null    object 
     9   Fare         891 non-null    float64
     10  Cabin        204 non-null    object 
     11  Embarked     889 non-null    object 
    dtypes: float64(2), int64(5), object(5)
    memory usage: 83.7+ KB
    


```python
print(f'Data size = {test.shape}')
test.head()
```

    Data size = (418, 11)
    




```python
test.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 418 entries, 0 to 417
    Data columns (total 11 columns):
     #   Column       Non-Null Count  Dtype  
    ---  ------       --------------  -----  
     0   PassengerId  418 non-null    int64  
     1   Pclass       418 non-null    int64  
     2   Name         418 non-null    object 
     3   Sex          418 non-null    object 
     4   Age          332 non-null    float64
     5   SibSp        418 non-null    int64  
     6   Parch        418 non-null    int64  
     7   Ticket       418 non-null    object 
     8   Fare         417 non-null    float64
     9   Cabin        91 non-null     object 
     10  Embarked     418 non-null    object 
    dtypes: float64(2), int64(4), object(5)
    memory usage: 36.0+ KB
    

### 欠損値


```python
train.isna().sum()
```




    PassengerId      0
    Survived         0
    Pclass           0
    Name             0
    Sex              0
    Age            177
    SibSp            0
    Parch            0
    Ticket           0
    Fare             0
    Cabin          687
    Embarked         2
    dtype: int64




```python
test.isna().sum()
```




    PassengerId      0
    Pclass           0
    Name             0
    Sex              0
    Age             86
    SibSp            0
    Parch            0
    Ticket           0
    Fare             1
    Cabin          327
    Embarked         0
    dtype: int64



### 統計量


```python
train.describe()
```




```python
train['Fare'].count(), train['Fare'].mean(), train['Fare'].std(ddof=1), train['Fare'].min()
```




    (891, 32.204207968574636, 49.6934285971809, 0.0)




```python
train['Fare'].quantile(0.25), train['Fare'].median(), train['Fare'].quantile(0.75), train['Fare'].max(), 
```




    (7.9104, 14.4542, 31.0, 512.3292)



### 最頻値


```python
train['Pclass'].mode()
```




    0    3
    Name: Pclass, dtype: int64



### 値のリスト


```python
train['Pclass'].unique()
```




    array([3, 1, 2], dtype=int64)



### 値と件数


```python
train['Pclass'].value_counts()
```




    Pclass
    3    491
    1    216
    2    184
    Name: count, dtype: int64



### 特定条件のフィルタリング


```python
train[train['Survived'] == 1].head()
```





### ヒストグラム


```python
# ヒストグラムと値の数
fig, ax = plt.subplots(1, 2, figsize=(6,2))
train['Pclass'].hist(ax=ax[0])
train['Pclass'].value_counts().plot.bar(ax=ax[1])
plt.tight_layout()
```


    
![png](titanic01_files/titanic01_27_0.png)
    



```python
# 指定した特徴量
features = ['Age', 'SibSp', 'Fare']
fig, ax = plt.subplots(1, 3, figsize=(9, 2))
for i, kind in enumerate(features):
    ax[i].hist(train[kind], bins=20)
    ax[i].set_title(kind)
plt.tight_layout()
```


    
![png](titanic01_files/titanic01_28_0.png)
    



```python
# df で表示可能な特徴量
fig = plt.figure(figsize=(9,6))
train.hist(ax=fig.gca(), bins=20)
plt.tight_layout()   
```

    C:\Users\jy810251\AppData\Local\Temp\ipykernel_19060\3876723797.py:3: UserWarning: To output multiple subplots, the figure containing the passed axes is being cleared.
      train.hist(ax=fig.gca(), bins=20)
    


    
![png](titanic01_files/titanic01_29_1.png)
    



```python
# 重ね合わせ
plt.figure(figsize=(4, 2))
train[train['Survived'] == 0]['Age'].hist(bins=20, alpha=0.3, color='red')
train[train['Survived'] == 1]['Age'].hist(bins=20, alpha=0.3, color='blue')
```




    <Axes: >




    
![png](titanic01_files/titanic01_30_1.png)
    


### クロス集計


```python
pd.crosstab(train['Survived'], train['Pclass'])
```




```python
fig, ax = plt.subplots(1, 2, figsize=(6,2))
pd.crosstab(train['Pclass'], train['Survived']).plot.bar(ax=ax[0])
pd.crosstab(train['Survived'], train['Pclass']).plot.bar(ax=ax[1])
```




    <Axes: xlabel='Survived'>




    
![png](titanic01_files/titanic01_33_1.png)
    



```python
# Seaborn bar
fig, ax = plt.subplots(figsize=(3,2))
sns.countplot(x='Pclass', hue='Survived', data=train, ax=ax)
```




    <Axes: xlabel='Pclass', ylabel='count'>




    
![png](titanic01_files/titanic01_34_1.png)
    



```python
# Seaborn scatter
fig, ax = plt.subplots(figsize=(3,2))
ax = plt.scatter(train['Age'], train['Fare'], s=6)
plt.show()
```


    
![png](titanic01_files/titanic01_35_0.png)
    


### Tips


```python
%%time

# 実行時間
a = [n for n in range(10**6)]

# コメント
_='''
複数行コメント（※実際は複数行の文字列）
読み捨て用変数（とりあえず_）に値を設定することで、
最終行をコメントとしても出力には表示されない
'''

```

    CPU times: total: 78.1 ms
    Wall time: 69.4 ms
    

### 前処理
- カテゴリー変数の数値変換(One-hot エンコーディング)
- カテゴリー変数の数値変換(数値への変換)


```python
# カテゴリー変数の数値変換(One-hot エンコーディング)
pd.get_dummies(train, columns=['Embarked'], dtype=int).head(3)
```



```python
# カテゴリー変数の数値変換(数値への変換)
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
le.fit_transform(train['Sex'])[:10]

# カテゴリー変数の数値変換(数値への変換)
pd.factorize(train['Sex'])[0][:10]

# カテゴリー変数の数値変換(数値への変換)
train['Sex'].map({'male': 0, 'female': 1})[:10]
```




    0    0
    1    1
    2    1
    3    1
    4    0
    5    0
    6    0
    7    0
    8    1
    9    1
    Name: Sex, dtype: int64



### 欠損値の補完
- ゼロで補完
- 平均値で補完
- その他の値で補完


```python
# ゼロで補完
train['Age'].fillna(0, inplace=True)
test['Age'].fillna(0, inplace=True)
```

### 特徴量の正規化(標準化)


```python
# 年齢の正規化
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
sc.fit_transform(train[['Age']])[:10]
```




    array([[-0.10231279],
           [ 0.80749164],
           [ 0.12513832],
           [ 0.63690331],
           [ 0.63690331],
           [-1.35329389],
           [ 1.71729608],
           [-1.23956834],
           [ 0.18200109],
           [-0.55721501]])



### 特徴量の選択


```python
# 必要特徴量以外の削除
drop_columns = ['PassengerId', 'Name', 'SibSp', 'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked']
train.drop(drop_columns, axis=1).head(3)
```




### モデル作成、学習、予測


```python
# 予測列名
cols = ['Pclass', 'Age']
# 学習用
X_train = train[cols]
y_train = train['Survived']
# 予測用
X_test = test[cols]
```


```python
# ロジスティック回帰
from sklearn.linear_model import LogisticRegression
# モデル作成
model = LogisticRegression(solver='liblinear', random_state=42)
# 学習
model.fit(X_train, y_train)
# 予測
y_test = model.predict(X_test)
# 生存者のカウント
pd.Series(y_test).value_counts()
```




    0    302
    1    116
    Name: count, dtype: int64




```python
# ランダムフォレスト
from sklearn.ensemble import RandomForestClassifier
# モデル作成
model = RandomForestClassifier(n_estimators=100, max_depth=3, random_state=42)
# 学習
model.fit(X_train, y_train)
# 予測
y_test = model.predict(X_test)
# 生存者のカウント
pd.Series(y_test).value_counts()
```




    0    314
    1    104
    Name: count, dtype: int64



## 精度向上の取り組み方

### 精度の検証について
- 1日にサブミットできる回数には制限がある
- 手元でスコア確認する仕組みが必要
- 実世界でも未知のデータに対応する必要がある

### まずやってみること
- 使っていない特徴量
- 欠損値を考える

### ホールドアウト検証


```python
# ホールドアウト検証
from sklearn.model_selection import train_test_split

train_x, valid_x, train_y, valid_y = train_test_split(X_train, y_train, test_size=0.2, random_state=0)
```

### 交差検証(Cross Validation)


```python
from sklearn.model_selection import KFold

folds = KFold(n_splits=3)

for fold_, (trn_, val_) in enumerate(folds.split(X_train, y_train)):
    trn_x, trn_y = X_train.iloc[trn_], y_train.iloc[trn_]
    val_x, val_y = X_train.iloc[val_], y_train.iloc[val_]
```

## まとめ
- 機械学習は、ライブラリの使い方、統計、数学など幅広い知識が求められる
- Kaggle を積極的に活用し、詰まってきたら適宜勉強をしていくのがおすすめ
