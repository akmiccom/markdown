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

## Basic method

```Python
seaborn.barplot(x=None, y=None, hue=None, data=None, order=None, hue_order=None,
                estimator=<function mean>, ci=95, n_boot=1000, units=None,
                orient=None, color=None, palette=None, saturation=0.75,
                errcolor='.26', errwidth=None, capsize=None, ax=None, **kwargs)
```

```Python
sns.scatterplot(x="Age", y="Fare", hue="Survived", data=df_1)
```
### 引数 (Argument)

| argument |                    value |
| :------: | -----------------------: |
|   x, y   |         x=縦軸、y=横方向 |
|   hue    |       各軸を分割する列名 |
|   data   | 集計対象のデータフレーム |
