---
title : How to Markdown
Category : Programming
Author : Makoto Yaugchi
---

# How to Markdown

Markdownはシンプルで簡単なマークアップ言語で、テキストを装飾したり構造化したりするのに便利です。
Markdownの基本的な概要、使い方、および基本的な書き方を解説します。

[TOC]

## Markdown 記法の概要

### Markdownとは

Markdownは、テキストを簡単に装飾するための軽量なマークアップ言語です。もともとはプレーンテキストの中にタグえお埋め込むことなく、HTMLを書くためのものとして開発されました。今では、多くのウェブプラットフォームやツールで広く使用されています。

### 基本原則
##### シンプル
- 読み書きが容易で、HTMLなどの冗長なコードを排除します
##### 軽量
- 短いコードで効果的な装飾ができます
##### 拡張性
- HTMLを使ってさらに高度な編集ができます

## Markdown の基本的な書き方
##### ファイルの拡張子 .md
##### テキストエディタで編集可能
##### オンラインプラットフォーム(Github, GitLab, Bitbucket etc.)でリアルタイムプレビュー可能

##### 使えるEditor
- Visual Studio Code
- Atom
- MacDown

Markdownの基本的な使い方を把握して、これを活用し簡潔で読みやすい記事を書いてみましょう。

## Markdownの 使い方

### テキストの装飾の基本

##### Basic Syntax

|     Element     | Markdown Syntax                                  |       note       |
| :-------------: | :----------------------------------------------- | :--------------: |
|   comment out   | `<!-- -->`                                       |  コメントアウト  |
|     Heading     | # h1 <br> # h2                                   |      見出し      |
|      Bold       | \*\*bold text\*\*                                |       強調       |
|     italic      | \*italicezed text\*                              |    イタリック    |
|   Blockquote    | > blockquote                                     |       引用       |
|  Ordered List   | 1. <br> 2. <br> 3.                               |  番号付きリスト  |
| unordered List  | - <br> - <br> -                                  |   番号内リスト   |
|      Code       | code <br>  \```python<br>```                     |   コードの表記   |
|      Code       | `print('Hello world!)`                           | インラインコード |
|      Link       | \[title](http://www.example.com)                 |      リンク      |
|      Image      | \!\[alt text](img/image.jpg)                     |       画像       |
|     Escape      | \                                                | 文字のエスケープ |
| Hoeizontal Rule | --- *** ___                                      |      水平線      |
|      Space      | \&thinsp;&nbsp; <br> &nbsp <br> &ensp <br> &emsp |     スペース     |

[Markdown Cheat Sheet](https://www.Markdownguide.org/cheat-sheet/)

### テキストの装飾の拡張
##### Extended Syntax

|   Element    | Markdown Syntax                                                                                                             |
| :----------: | :-------------------------------------------------------------------------------------------------------------------------- |
|    Table     | \| syntax \| description \| <br> \| ---- \| ---- \| <br> \| Header \| Title \|  <br> \| Paragraph \| Text \|                |
|   Footnote   | Here's a sentence with a footnote.[^1] <br> [^1]: This is the footnote                                                      |
|  Heading ID  | ### My Greate Heading {# custom-id }                                                                                        |
|  Highlight   | \==very important words.==                                                                                                  |
| Strikethrogh | \~~The world is flat~~                                                                                                      |
|    Emoji     | \:joy: &thinsp;&nbsp; [Copying and Pasting Emoji](https://www.Markdownguide.org/extended-syntax/#copying-and-pasting-emoji) |
|     Note     | \:::note info <br> Information <br> :::                                                                                     |
|  Subscript   | h~2~0                                                                                                                       |
| SuperScript  | X^2^                                                                                                                        |

## Mathjax Syntax

- [Mathjaxの使い方](https://www.eng.niigata-u.ac.jp/~nomoto/download/mathjax.pdf)

以下のように書くと数式のような分数が表現できる。複雑な数式も簡単に書くことができます
```
\$\$ \\frac{1}{2} \$\$
\\[ \\frac{1}{2} \\]
\frac{1}{2}
```

$$ \frac{1}{2} $$

### もっとMarkdownを使いこなす

