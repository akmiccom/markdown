---
title : seaborn Cheat Sheet
category : Cheat Sheets
author : Makoto Yaguchi
---

# seaborn Cheat Sheet

[seaborn documentation](https://seaborn.pydata.org)

[TOC]

## library

```Python
import seaborn as sns
```

## Basic method and argument

```Python
seaborn.barplot(x=None, y=None, hue=None, data=None, order=None, hue_order=None,
                estimator=<function mean>, ci=95, n_boot=1000, units=None,
                orient=None, color=None, palette=None, saturation=0.75,
                errcolor='.26', errwidth=None, capsize=None, ax=None, **kwargs)
```

| argument |                    value |
| :------: | -----------------------: |
|   x, y   |         x=縦軸、y=横方向 |
|   hue    |       各軸を分割する列名 |
|   data   | 集計対象のデータフレーム |


### Examples
```Python
# scatterplot(散布図)
sns.scatterplot(x="Age", y="Fare", hue="Survived", data=df_1)
# relplot(複数配置)
sns.relplot(x="Age", y="Fare", hue="Survived", col="Pclass", row="Sex", data=df_1)
# rugplot(軸プロット)
sns.rugplot(x="Age", y="Fare", hue="Survived", data=df_1)
# stripplot(1変数散布図)
sns.stripplot(x="Pclass", y="Age", hue="Survived", data=df_1)
# catplot(stripplotの複数配置)
sns.catplot(x="Pclass", y="Age", hue="Survived", col="Embarked", row="Sex", data=df_1)

```
