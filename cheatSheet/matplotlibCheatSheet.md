---
title : Matplotlib Cheat Sheet
category : Cheat Sheets
author : Makoto Yaguchi
---

# Matplotlib Cheat Sheet

[Matplotlib documentation](https://matplotlib.org/stable/)

[TOC]

## import and data
```Python
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(0, 10, 0.1)
sin = np.sin(x)
cos = np.cos(x)
```

## Display Simple Graph
```Python
plt.plot(x, sin, label='sin')   # サイン波と凡例の文字
plt.plot(x, cos, label='cos')
plt.title('sin and cos curve')  # グラフのタイトル
plt.xlabel('Time')              # x軸のラベル
plt.ylabel('Amplitude')         # y軸のラベル
plt.legend()                    # 凡例
plt.show()                      # 表示
```

## 複数のグラフの表示 1行3列
```Python
# プロット領域 1行3列の配列
fig, (ax1, ax2, ax3) = plt.subplots(1, 3, figsize=(15, 3))

# ax1 データのプロット
ax1.bar([1,2,3], [3,4,5])
# ax2 データのプロット
ax2.barh([0.5, 1, 2.5], [0,1,2])
# ax3 データのプロット
ax3.plot(x, sin, label='sin')
ax3.set_title('sin')
ax3.set_xlabel('Time')
ax3.set_ylabel('Amplitude')
plt.legend()
plt.tight_layout()
plt.show()
```

## 複数のグラフの表示 2行2列
```Python
# プロット領域の初期化(今回は1行2列の配列)
fig, ax = plt.subplots(2, 2, figsize=(12, 6))
# データのプロット
ax[0][0].bar([1,2,3], [3,4,5])
ax[0][1].barh([0.5, 1, 2.5], [0,1,2])
ax[1][0].plot(x, sin, label='sin')
ax[1][1].plot(x, cos, label='cos')
plt.legend()
plt.tight_layout()
plt.show()
```

## グラフの保存
```Python
plt.savefig('hogehoge.png')
```


## Method
|       記法        |           グラフの種類           |
| :---------------: | :------------------------------: |
|    Axes.plot()    |           折れ線グラフ           |
|  Axes.scatter()   |              散布図              |
|    Axes.bar()     |            縦棒グラフ            |
|    Axes.barh()    |            横棒グラフ            |
|    Axes.hist()    |           ヒストグラム           |
|  Axes.boxplot()   |         ボックスプロット         |
| Axes.violinplot() |        バイオリンプロット        |
|  Axes.contour()   |         コンタープロット         |
|   Axes.pcolor()   | 擬似カラープロット(ヒートマップ) |
|   Axes.imshow()   |               画像               |
|  Axes.axhline()   |              水平線              |
|  Axes.axvline()   |              垂直線              |

## Setting
|       記法        |    操作の内容    |
| :---------------: | :--------------: |
| Axes.set_title()  |  タイトルを設定  |
| Axes.set_xlabel() | x軸の名前を設定  |
| Axes.set_ylabel() | y軸の名前を設定  |
|  Axes.set_xlim()  | x軸の範囲を指定  |
|  Axes.set_ylim()  | y軸の範囲を指定  |
|   Axes.legend()   |    凡例を表示    |
|    Axes.grid()    | グリッド線を表示 |

## Line Color and Style
|   文字    |     色     |       |  記法   |   線種   |
| :-------: | :--------: | :---: | :-----: | :------: |
| color="b" |    (青)    |       | ls=':'  |   点線   |
| color="g" |    (緑)    |       | ls='-.' | 一点鎖線 |
| color="r" |    (赤)    |       | ls='--' |   破線   |
| color="c" |  (シアン)  |       | ls='-'  |   実線   |
| color="m" | (マゼンダ) |
| color="y" | (イエロー) |
| color="k" |    (黒)    |
| color="w" |    (白)    |

## Marker
|    記法    | マーカー |       |    記法    |     マーカー      |
| :--------: | :------: | :---: | :--------: | :---------------: |
| marker='.' |    点    |       | marker='*' |        星         |
| marker=',' | ピクセル |       | marker='1' |         Y         |
| marker='o' |    丸    |       | marker='2' |    Y(上下反転)    |
| marker='v' | 下三角形 |       | marker='3' |  Y(90度時計回り)  |
| marker='^' |  三角形  |       | marker='4' | Y(90度反時計周り) |
| marker='<' | 左三角形 |       | marker='+' |         +         |
| marker='>' | 右三角形 |       | marker='x' |         x         |
| marker='s' |  四角形  |       | marker='X' |     x(filled)     |
| marker='p' |  五角形  |       | marker='D' |      ひし形       |
| marker='h' |  六角形  |       | marker='d' |    細いひし形     |
| marker='8' |  八角形  |       | marker=''  |   マーカー無し    |
