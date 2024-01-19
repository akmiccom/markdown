---
title : MathJax Cheat Sheet
category : Cheat Sheets
author : Makoto Yaguchi
---

# MathJax Cheat Sheet
[MathJax Documentation](https://docs.mathjax.org/en/latest/)

[MathJax の使い方](https://www.eng.niigata-u.ac.jp/~nomoto/download/mathjax.pdf)

MathJaxは、LaTeX、MathML、およびAsciiMath表記用のオープンソースJavaScriptディスプレイエンジンで、最新のブラウザーすべてで動作し、スクリーンリーダーなどの支援テクノロジーを組み込みにサポートしています。

[TOC]

# コマンド一覧

### マトリックス
|             Command              |  表示  |             Command              |   表示   |
| :------------------------------: | :----: | :------------------------------: | :------: |
| \\\begin{pmatrix}～\end{pmatrix} | 丸括弧 | \\\begin{vmatrix}～\end{vmatrix} |   縦棒   |
| \\\begin{bmatrix}～\end{bmatrix} | 角括弧 | \\\begin{Vmatrix}～\end{Vmatrix} | 二重縦棒 |
| \\\begin{Bmatrix}～\end{Bmatrix} | 波括弧 |  \\\begin{matrix}～\end{matrix}  | 括弧なし |

## 分数、平方根、二項係数など
|   Command   |     表示      |   Command   |     表示      |   Command    |      表示      |
| :---------: | :-----------: | :---------: | :-----------: | :----------: | :------------: |
| \frac{a}{b} | $\frac{a}{b}$ |    _nC_r    |    $_nC_r$    | \binom{n}{r} | $\binom{n}{r}$ |
|  \sqrt{x}   |  $\sqrt{x}$   | \sqrt[n]{x} | $\sqrt[n]{x}$ |

## スペース 括弧
| Command |      表示      | Command | 表示  |  Command  |  表示   |
| :-----: | :------------: | :-----: | :---: | :-------: | :-----: |
|   \␣    | 小さいスペース |  \(x\)  | $(x)$ |   \|x\|   | $\|x\|$ |
|  \quad  | 大きいスペース |  \[x\]  | $[x]$ | \|\|x\|\| |  $∥x∥$  |
| \qquad  | \quad の 2 倍  |  \{x\}  | ${x}$ |

## ギリシャ文字
| Command  |    表示    |   Command   |     表示      |  Command  |    表示     | Command |   表示   |
| :------: | :--------: | :---------: | :-----------: | :-------: | :---------: | :-----: | :------: |
|  \alpha  |  $\alpha$  |    \beta    |    $\beta$    |  \gamma   |  $\gamma$   | \delta  | $\delta$ |
| \epsilon | $\epsilon$ | \varepsilon | $\varepsilon$ |   \zeta   |   $\zeta$   |  \eta   |  $\eta$  |
|  \theta  |  $\theta$  |  \vartheta  |  $\vartheta$  |   \iota   |   $\iota$   | \kappa  | $\kappa$ |
| \lambda  | $\lambda$  |     \mu     |     $\mu$     |    \nu    |    $\nu$    |   \xi   |  $\xi$   |
|    o     |    $o$     |     \pi     |     $\pi$     |  \varpi   |  $\varpi$   |  \rho   |  $\rho$  |
| \varrho  | $\varrho$  |   \sigma    |   $\sigma$    | \varsigma | $\varsigma$ |  \tau   |  $\tau$  |
| \upsilon | $\upsilon$ |    \phi     |    $\phi$     |  \varphi  |  $\varphi$  |  \chi   |  $\chi$  |
|   \psi   |   $\psi$   |   \omega    |   $\omega$    |

## ギリシャ文字 大文字
| Command |   表示   |  Command  |    表示     | Command  |    表示    |   Command   |     表示      |
| :-----: | :------: | :-------: | :---------: | :------: | :--------: | :---------: | :-----------: |
| \Gamma  | $\Gamma$ | \varGamma | $\varGamma$ |  \Delta  |  $\Delta$  | \varDelata  |  $\varDelta$  |
| \Theta  | $\Theta$ | \varTheta | $\varTheta$ | \Lambda  | $\Lambda$  | \varLambda  | $\varLambda$  |
|   \Xi   |  $\Xi$   |  \varXi   |  $\varXi$   |   \Pi    |   $\Pi$    |   \varPi    |   $\varPi$    |
| \Sigma  | $\Sigma$ | \varSigma | $\varSigma$ | \Upsilon | $\Upsilon$ | \varUpsilon | $\varUpsilon$ |
|  \Phi   |  $\Phi$  |  \varPhi  |  $\varPhi$  |   \Psi   |   $\Psi$   |   \varPsi   |   $\varPsi$   |
| \Omega  | $\Omega$ | \varOmega | $\varOmega$ |

## 二項演算子
| Command |   表示   | Command |   表示   |  Command   |   表示    |
| :-----: | :------: | :-----: | :------: | :--------: | :-------: |
|    +    |   $+$    |  \div   |  $\div$  |  \bullet   | $\bullet$ |
|    -    |   $−$    |  \ast   |  $\ast$  | \backslash |     \     |
|   \pm   |  $\pm$   |  \star  | $\star$  |    \cap    |  $\cap$   |
| \times  | $\times$ |  \cdot  | $\cdots$ |    \cup    |  $\cup$   |

## 関係演算子
|  Command   |     表示     |    Command     |       表示       |  Command  |    表示     |   Command    |      表示      |
| :--------: | :----------: | :------------: | :--------------: | :-------: | :---------: | :----------: | :------------: |
|     =      |     $=$      |     \cong      |     $\cong$      |    \lt    |    $\lt$    |   \lesssim   |   $\lesssim$   |
|    \neq    |    $\neq$    |    \propto     |    $\propto$     |    \gt    |    $\gt$    |   \gtrsim    |   $\gtrsim$    |
|   \doteq   |   $\doteq$   |   \varpropto   |   $\varpropto$   |    \ll    |    $\ll$    |   \subset    |   $\subset$    |
| \doteqdot  | $\doteqdot$  |     \perp      |     $\perp$      |    \gg    |    $\gg$    |   \supset    |   $\supset$    |
|   \equiv   |   $\equiv$   |      \mid      |      $\mid$      |   \lll    |   $\lll$    |  \subseteq   |  $\subseteq$   |
|    \sim    |    $\sim$    |   \shortmid    |   $\shortmid$    |   \ggg    |   $\ggg$    |  \supseteq   |  $\supseteq$   |
|  \backsim  |  $\backsim$  |   \parallel    |   $\parallel$    | \le, \leq |   $\leq$    |  \subseteqq  |  $\subseteqq$  |
|   \simeq   |   $\simeq$   | \shortparallel | $\shortparallel$ | \ge, \geq |   $\geq$    |  \supseteqq  |  $\supseteqq$  |
| \backsimeq | $\backsimeq$ |   \therefore   |   $\therefore$   |   \leqq   |   $\leqq$   |     \in      |     $\in$      |
|   \eqsim   |   $\eqsim$   |    \because    |    $\because$    |   \geqq   |   $\geqq$   |     \ni      |     $\ni$      |
|  \approx   |  $\approx$   | \risingdotseq  | $\risingdotseq$  | \leqslant | $\leqslant$ |    \notin    |    $\notin$    |
| \approxeq  | $\approxeq$  | \fallingdotseq | $\fallingdotseq$ | \geqslant | $\geqslant$ | \backepsilon | $\backepsilon$ |


## 関数等
| Command |   表示    | Command |  表示   | Command |  表示   | Command |  表示  |
| :-----: | :-------: | :-----: | :-----: | :-----: | :-----: | :-----: | :----: |
|  \sin   |  $\sin$   |  \sinh  | $\sinh$ |   \ln   |  $\ln$  |  \min   | $\min$ |
|  \cos   |  $\cos$   |  \cosh  | $\cosh$ |   \lg   |  $\lg$  |  \max   | $\max$ |
|  \tan   |  $\tan$   |  \tanh  | $\tanh$ |  \deg   | $\deg$  |  \inf   | $\inf$ |
| \arcsin | $\arcsin$ |  \coth  | $\coth$ |  \dim   | $\dim$  |  \det   | $\det$ |
| \arccos | $\arccos$ |  \exp   | $\exp$  |  \bmod  | $\bmod$ |  \gcd   | $\gcd$ |
| \arctan | $\arctan$ |  \log   | $\log$  |  \lim   | $\lim$  |

## 記号
|   Command   |     表示      | Command |   表示   |   Command    |      表示      |   Command    |      表示      |
| :---------: | :-----------: | :-----: | :------: | :----------: | :------------: | :----------: | :------------: |
|  \emptyset  |  $\emptyset$  |  \ell   |  $\ell$  |  \triangle   |  $\triangle$   |  \spadesuit  |  $\spadesuit$  |
| \varnothing | $\varnothing$ |   \Re   |  $\Re$   |   \square    |   $\square$    |  \heartsuit  |  $\heartsuit$  |
|   \infty    |   $\infty$    |   \Im   |  $\Im$   | \blacksquare | $\blacksquare$ | \diamondsuit | $\diamondsuit$ |
|  \partial   |  $\partial$   | \nabla  | $\nabla$ |   \bigstar   |   $\bigstar$   |  \clubsuit   |  $\clubsuit$   |

## 大きな記号
| Command |   表示    |  Command  |    表示     |  Command   |     表示     | Command |   表示   |
| :-----: | :-------: | :-------: | :---------: | :--------: | :----------: | :-----: | :------: |
|  \sum   |  $\sum$   |  \bigcup  |  $\bigcup$  |  \bigvee   |  $\bigvee$   |  \int   |  $\int$  |
|  \prod  |  $\prod$  | \biguplus | $\biguplus$ | \bigoplus  | $\bigoplus$  |  \oint  | $\oint$  |
| \coprod | $\coprod$ | \bigsqcup | $\bigsqcup$ | \bigotimes | $\bigotimes$ |  \iint  | $\iint$  |
| \bigcap | $\bigcap$ | \bigwedge | $\bigwedge$ |  \bigodot  |  $\bigodot$  | \iiint  | $\iiint$ |

## 上付き記号
| Command |   表示    | Command  |    表示    |  Command  |    表示     |
| :-----: | :-------: | :------: | :--------: | :-------: | :---------: |
| \vec{x} | $\vec{x}$ | \dot{x}  | $\dot{x}$  |  \hat{x}  |  $\hat{x}$  |
| \bar{x} | $\bar{x}$ | \ddot{x} | $\ddot{x}$ | \tilde{x} | $\tilde{x}$ |

## 点々
| Command |   表示   | Command |   表示   | Command |   表示   | Command |   表示   |
| :-----: | :------: | :-----: | :------: | :-----: | :------: | :-----: | :------: |
| \cdots  | $\cdots$ | \ldots  | $\ldots$ | \vdots  | $\vdots$ | \ddots  | $\ddots$ |

## 矢印
|      Command      |     表示      |     Command     |       表示        |       Command       |         表示          |
| :---------------: | :-----------: | :-------------: | :---------------: | :-----------------: | :-------------------: |
| \rightarrow, \to  | $\rightarrow$ |   \Rightarrow   |   $\Rightarrow$   |   \leftrightarrow   |   $\leftrightarrow$   |
| \leftarrow, \gets | $\leftarrow$  |   \Leftarrow    |   $\Leftarrow$    | \longleftrightarrow | $\longleftrightarrow$ |
|     \uparrow      |  $\uparrow$   | \longrightarrow | $\longrightarrow$ |       \mapsto       |       $\mapsto$       |
|    \downarrow     | $\downarrow$  | \longleftarrow  | $\longleftarrow$  |     \longmapsto     |     $\longmapsto$     |


# 記述サンプル
文中に書くとき → \$a \ne 0\$
- インラインモードで $a \ne 0$ と表示されます。
別行で書くとき → \$\$a \ne 0\$\$
- ブロックノードで以下のように表示されます。$$a \ne 0$$

```HTML
<body>
    When \(a \ne 0\), there are two solutions to \(ax^2 + bx + c = 0\) and they are
    $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
</body>
```

### 分数、±、平方根、階乗、数式番号
$$ x = \frac{-b\pm\sqrt{b^{2}-4ac}}{2a} \tag{1} $$
```HTML
$$ x = \frac{-b\pm\sqrt{b^{2}-4ac}}{2a} \tag{1} $$
```
|  Command  |   表示   |
| :-------: | :------: |
| \frac{}{} |   分数   |
|    \pm    |    ±     |
|  \sqrt{}  |  平方根  |
|  a^{n+1}  |   階乗   |
|  \tag{1}  | 数式番号 |

### 総和記号と和の上限下限、点々
$$ \sum_{k=1}^{n} a_{k} = a_{1} + a_{2} + \dots + a_{n} $$
```HTML
$$ \sum_{k=1}^{n} a_{k} = a_{1} + a_{2} + \dots + a_{n} $$
```
|  Command   |    表示    |
| :--------: | :--------: |
| \sum_{}^{} |    分数    |
|   \cdots   | 中央の点々 |

### ガウス積分
$$ \int_{-\infty}^{\infty} e^{-x^{2}} \, dx = \sqrt{\pi} $$
```HTML
$$ \int_{-\infty}^{\infty} e^{-x^{2}} \, dx = \sqrt{\pi} $$
```
|  Command   |    表示    |
| :--------: | :--------: |
| \int_{}^{} |    積分    |
|   \infty   |    無限    |
|     \,     | スペース小 |
|    \pi     |   π記号    |

### 複数行表示 位置揃え

$$ \begin{align}
\cos 2\theta
&= \cos^{2} \theta - \sin^{2} \theta  \\
&= 2\cos^{2} \theta - 1  \\
&= 1 - 2\sin^{2} \theta
\end{align}
$$

```HTML
$$ \begin{align}
\cos 2\theta &= \cos^{2} \theta - \sin^{2} \theta  \\
&= 2\cos^{2} \theta - 1 \\
&= 1 - 2\sin^{2} \theta
\end{align} $$
```
|          Command           |      表示      |
| :------------------------: | :------------: |
| \begin{align}～\end{align} | 別行立ての数式 |
|             \\             |      改行      |
|             &              |  位置を揃える  |

### 複数行の表示 条件分け
$$ |x| = \begin{cases}
x & x \ge 0 のとき \\
-x & x \lt 0 のとき
\end{cases} $$

```HTML
$$
|x| = \begin{cases}
x & x \ge 0 のとき \\
-x & x \lt 0 のとき
\end{cases}
$$
```
|          Command           |   表示   |
| :------------------------: | :------: |
| \begin{cases}～\end{cases} | 条件分け |
|            \lt             |  $\lt$   |
|            \gt             |  $\gt$   |
|            \leq            |  $\leq$  |
|            \geq            |  $\geq$  |
|            \neq            |  $\neq$  |

### 行列
$$
A = \begin{pmatrix}
a_{11} & a_{12} & \ldots & a_{1n} \\
a_{21} & a_{22} & \ldots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \ldots & a_{nn}
\end{pmatrix}
$$

```HTML
$$
A = \begin{pmatrix}
a_{11} & a_{12} & \ldots & a_{1n} \\
a_{21} & a_{22} & \ldots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \ldots & a_{nn}
\end{pmatrix}
$$
```
|            Command             |   表示   |
| :----------------------------: | :------: |
| \begin{pmatrix}～\end{pmatrix} |  丸括弧  |
| \begin{bmatrix}～\end{bmatrix} |  角括弧  |
| \begin{Bmatrix}～\end{Bmatrix} |  波括弧  |
| \begin{vmatrix}～\end{vmatrix} |   縦棒   |
| \begin{Vmatrix}～\end{Vmatrix} | 二重縦棒 |
|  \begin{matrix}～\end{matrix}  | 括弧なし |
|             \cdots             | $\cdots$ |
|             \ldots             | $\ldots$ |
|             \vdots             | $\vdots$ |
|             \ddots             | $\ddots$ |

### 集合記号
$$ A \cup B = \{ x | x \in A \wedge x \in B \} $$
```HTML
$$ A \cup B = \{ x | x \in A \wedge x \in B \} $$
```
| Command |      表示       |
| :-----: | :-------------: |
| \\{ \\} | 波括弧(\が必要) |
|  \cup   |  和集合$\cup$   |
|  \cap   |  積集合$\cap$   |

### 二項係数
$$ _nC_r = \binom{n}{r} = \frac{n!}{r!(n-r)!} $$
```HTML
$$ _nC_r = \binom{n}{r} = \frac{n!}{r!(n-r)!} $$
```
|   Command    |      表示      |
| :----------: | :------------: |
|    _nC_r     |    $_nC_r$     |
| \binom{n}{r} | $\binom{n}{r}$ |


# MathJax の使い方
```html
<!DOCTYPE html>
<html>
<head>
    <title>MathJax TeX Test Page</title>
    <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
    <script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>
</head>
<body>
    When \(a \ne 0\), there are two solutions to \(ax^2 + bx + c = 0\) and they are
    $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
</body>
</html>
```