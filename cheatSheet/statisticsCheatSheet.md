---
title : Statistics Cheat Sheet
category : Cheat Sheets
author : Makoto Yaguchi
---

# Statistics Cheat Sheet

[TOC]

## 質的変数と量的変数による尺度

|   尺度   |                  意味                   |      利用統計量      |        例        |
| :------: | :-------------------------------------: | :------------------: | :--------------: |
| 名義尺度 |             同じ値かどうか              |     度数、最頻値     |    性別、職業    |
| 順序尺度 |                大小関係                 |  + 中央値、四分位数  |     成績評価     |
| 間隔尺度 |  大小関係と差、0は相対的な意味のみ持つ  |   + 平均、標準偏差   | 摂氏温度、偏差値 |
| 比例尺度 | 大小関係と差・比、0は絶対的な意味を持つ | + 変動係数、幾何平均 |    身長、年齢    |


## 5数要約

| 統計量 | 表記  |       |    統計量    |  表記  |
| :----: | :---: | :---: | :----------: | :----: |
| 最小値 |  min  |       | 第一四分位数 |   Q1   |  |
| 最大値 |  max  |       |    中央値    | median |  |
| 最頻値 | mode  |       | 第三四分位数 |   Q3   |  |

## 統計学の主な統計量

|     統計量     |       表記        |                                       数式                                        |
| :------------: | :---------------: | :-------------------------------------------------------------------------------: |
|  平均(期待値)  |     $\bar{x}$     |                     $\bar{x} = \frac{1}{n} \sum_{i=1}^n x_i$                      |
|      分散      |   $\sigma_x^2$    |              $\sigma_x^2 = \frac{1}{n} \sum_{i=1}^n (x_i-\bar{x})^2$              |
|    不偏分散    |   $\hat{\sigma}_x^2$    |  $\hat{\sigma}_x^2 = \frac{1}{n-1} \sum_{i=1}^n (x_i-\bar{x})^2$              |
|    標準偏差    |    $\sigma_x$     |                           $\sigma_x = \sqrt{\sigma^2}$                            |
|(不偏)標準偏差    |    $\hat{\sigma}_x$|        $\hat{\sigma}_x = \sqrt{\hat{\sigma}_x^2}$                            |
|    変動係数    |       $CV$        |                          $CV = \frac{\sigma_x}{\bar{x}}$                          |
|     共分散     |   $\sigma_{xy}$   |        $\sigma_{xy} = \frac{1}{n}\sum_{i=1}^n (x_i-\bar{x})(y_i-\bar{y})$         |
|    相関係数    |     $r_{xy}$      |                 $r_{xy} = \frac{\sigma_{xy}}{\sigma_x \sigma_y}$                  |
|   偏相関係数   | $r_{(yz\cdot x)}$ | $r_{(yz\cdot x)}=\frac{r_{yx}-r_{xy}r_{xz}}{\sqrt{1-r_{xy}^2} \sqrt{1-r_{xz}^2}}$ |
| 回帰係数(傾き) |   $\hat{\beta}$   |          $\hat{\beta} = \frac{s_{xy}}{s_{x}^2} = r_{xy}\frac{s_y}{s_x}$           |
| 回帰係数(切片) |  $\hat{\alpha}$   |                  $\hat{\alpha} = \bar{y} - \hat{\beta} \bar{x}$                   |
|    回帰直線    |         -         |                      $\hat{y} = \hat{\beta}x + \hat{\alpha}$                      |
|    決定係数    |       $R^2$       |                                 $R^2 = r_{sy}^2$                                  |

### 確率密度関数から求める期待値と分散

- 離散型の期待値、分散
$$E[X]=\sum_i x_i f(x_i) \ , \quad V[X]=\sum_i (x_i - \mu)^2 f(x_i)$$        
- 連続型の期待値、分散
$$E[X]=\int_{-\infty}^{\infty} x f(x)dx \ , \quad V[X]=\int_{-\infty}^{\infty} (x-\mu)^2 f(x)dx$$ 

### モーメント(積率)と4つの統計量
|                         |     表示      | 原点回りの $r$ 次モーメント(積率)$\downarrow$ |       $r=0, 1$ の場合 $\downarrow$       |
| :---------------------: | :-----------: | :-------------------------------------------: | :--------------------------------------: |
|       **定義式**        | $\rightarrow$ |                $\mu_r=E(X^r)$                 | $\ast \ \mu_0\equiv 0, \ \mu_1'\equiv 1$ |
| 期待値 (expected value) |     $\mu$     |                $\mu_1=E(X)^1$                 |               $\mu=\mu_1$                |
|                         |               | **期待値回りの $r$ 次モーメント**$\downarrow$ |    **標準化モーメント** $\downarrow$     |
|       **定義式**        | $\rightarrow$ |              $\mu_r'=E(X-\mu)^r$              |   $\alpha_r=E(\frac{X-\mu}{\sigma})^r$   |
|     分散 (variance)     |  $\sigma^2$   |              $\mu_2'=E(X-\mu)^2$              |            $\sigma^2=\mu_2'$             |
|     歪度 (skewness)     |  $\alpha^3$   |              $\mu_3'=E(X-\mu)^3$              |       $\alpha_3=\mu_3' / \sigma^3$       |
|     尖度 (kurtosis)     |  $\alpha^4$   |              $\mu_4'=E(X-\mu)^4$              |       $\alpha_4=\mu_4' /\sigma^4$        |



### 確率分布

|    確率分布    |                                 確率関数                                 |       期待値        |         分散          |
| :------------: | :----------------------------------------------------------------------: | :-----------------: | :-------------------: |
| ベルヌーイ分布 |                        $P(X=1) = p, \ P(X=0) = q$                        |         $p$         |         $pq$          |
|    二項分布    |                       $f(x) = {}_nC_x p^x q^{n-x}$                       |        $np$         |         $npq$         |
|  ポワソン分布  |    $f(x) = e^{-\lambda} \frac{\lambda^x}{x!} \ (n\rightarrow \infty)$    |      $\lambda$      |       $\lambda$       |
|    幾何分布    |                            $f(x) = pq^{x-1}$                             |    $\frac{1}{p}$    |    $\frac{q}{p^2}$    |
|    一様分布    |        $f(x) = \frac{1}{b-a} \ (a \leq x \leq b), \ 0 \ (other)$         |   $\frac{a+b}{2}$   | $\frac{(b-a)^2}{12}$  |
|    正規分布    | $f(x)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp\{-\frac{(x-\mu)^2}{2\sigma^2}\}$ |        $\mu$        |      $\sigma^2$       |
|  標準正規分布  |           $f(x) = \frac{1}{\sqrt{2\pi}} \exp (-\frac{x^2}{2})$           |         $0$         |          $1$          |
|    指数分布    |                       $f(t) = 1 - e^{-\lambda t}$                        | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |

### 標本分布

|   標本分布    |                                                                                                   |       |
| :-----------: | :-----------------------------------------------------------------------------------------------: | :---: |
| $\chi^2$ 分布 |                    $W = \frac{(n-1)\hat{\sigma}^2}{\sigma^2} \sim \chi^2(n-1)$                    |       |
|   $t$ 分布    |                   $t = \frac{\sqrt{n}(\bar{X}-\mu)}{\hat{\sigma}} \sim t(n-1)$                    |       |
|   $F$ 分布    | $F =\frac{\hat{\sigma_1}^2}{\sigma_1^2} \frac{\sigma_2^2}{\hat{\sigma_2}^2} \sim F(n_1-1, n_2-1)$ |       |


### チェビシェフの不等式

$$ P(|X-\mu|\geq k\sigma) \leq 1 / k^2 $$


### 変数の変換