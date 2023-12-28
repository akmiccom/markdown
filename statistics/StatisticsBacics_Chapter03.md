---
Title : 統計学入門 3章 まとめ
Category : Blog
Author : Makoto Yaguchi
---

# 統計学入門 3章 まとめ

[TOC]

## 2次元のデータとは
2次元のデータとは、変数の数がひとつでなく、2つの場合を言います。それ以上のときは、多次元データといいます。その関係を見るために相関や回帰といったものを使います。

- 相関 : $x, y$ を対等にみる見方やその方法
- 回帰 : $x$ から $y$ をみる

## 散布図と分割表
- 散布図 : 2次元平面にいくつかの点をプロットしたもので、2変数の関係を見る基本的なもの
- 分割表 : 質的データの場合には、分割表(クロス表)を使う

## 相関係数
相関係数 $r$ は 1 から -1 の間をとりこれを $r>0$ のときは正の相関といい、グラフは右上がりとなります。逆に $r<0$ のときは負の相関といい、グラフは右下がりとなります。

- ピアソンの積率相関係数 $r_{xy}$
$$
r_{xy} =\frac{Cov[X, Y]}{\sqrt{V[X]}\sqrt{V[Y]}} = 
\frac{\sum(x_i -\bar{x})(y_i -\bar{y})}{\sqrt{\sum(x_i -\bar{x})^2 \sqrt{\sum(y_i -\bar{y})^2}}}
$$

- 標準化したときのピアソンの積率相関係数
    - $z_i, w_i$ の共分散に等しくなる

$$ z_i = \frac{x_i - \bar{x}}{S_x} \ ,  \quad w_i = \frac{y_i - \bar{y}}{S_y} $$

$$ r_{xy} = \frac{1}{n} \sum z_i w_i $$

相関係数が高いと相関関係が高いと言えますが、必ずしも二つのデータの間に因果関係があるということではないことに注意する必要があります。
そのような場合を見かけ上の相関といい、偏相関係数を使って判断することができます。

- 偏相関係数
$$
r_{12\cdot3} = \frac{r_{12}-r_{13}r_{23}}{\sqrt{1-r_{13}^2}\sqrt{1-r_{23}^2}}
$$

全体では相関関係が無いように見えるが、層別(地域、性別等)で見ると相関がみられることがあるので調べる際には注意する必要があなます。

また、積率相関係数はデータが質的変数のときに使われますが、順位 $rank R_i, R'_i$ の間の相関を見る場合には、順位相関係数を使います。同順位のときは一定の方法でタイ修正を行います。

- スピアマンの順位相関係数 $r_S$
    - $R_i, R'_i$ は比較する2つの順位

$$
r_S = 1 - \frac{6}{n^3-n}\sum(R_i-R'_i)^2
$$

- ケンドールの順位相関係数 $r_K$
    - 正順 : $G += 1$
    - 逆順 : $H -= 1$

$$
r_K = \frac{G-H}{n(n-1)/2}
$$

時系列データを扱う際には、$lag$ といった遅れを使った自己相関係数といったものを使ったりします。これは周期性、季節性などを見るために使われます。

また、$lag$ ごとの自己相関係数をグラフ化したものをコレログラムといいます。これにより自己相関の高低がどのくらいの $lag$ で発生しているのかがわかります。

- 自己相関係数

$$
r_h = \frac{\sum_{i=1}^{n-h} (x_i-\bar{x})(x_{i+h}-\bar{x})/(n-h)}{\sum_{i=1}^{n}(x_i - \bar{x})/n}
$$


## 直線および平面のあてはめ
散布図に直性をあてはめることで、片方のデータがわかればもう一つのデータを予測することができます。それを1次式で表し、傾きと切片を共分散や分散より予測することができます。その直線のあてはまり度を示す指標として決定係数(相関係数の二乗) $r^2$ というものがあります。これにより予測がどれくらい信頼できそうかを見ることができます。

- 単回帰分析
$$ y = \beta_1 + \beta_2 x $$

$$
\beta_2 = \frac{\sum(x_i - \bar{x})(y_i - \bar{y})}{\sum(x_i - \bar{x})^2}
= \frac{\sum x_i y_i - \sum n\bar{x}\bar{y}}{\sum x_i^2 - n\bar{x}^2}
$$

$$ \beta_1 = \bar{y} + \beta_2 \bar{x} $$

データが二つ以上ある場合は、重回帰分析になります。手計算では難しくなるため一般的に統計ソフトを使うことになります。直線であてはめるのが難しいことがわかっている場合は、多項式回帰というものになります。これは 2次式や3次式を使ってあてはめていく方法になります。

- 重回帰分析
$$ y = \beta_1 + \beta_2 x + \beta_3 x  $$
