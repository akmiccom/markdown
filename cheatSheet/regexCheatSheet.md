---
title : Regex Cheat Sheet
category : Cheat Sheets
author : Makoto Yaguchi
---

# Regex Cheat Sheet
[Regex Cheat Sheet](https://www.datacamp.com/cheat-sheet/regular-expresso)

[正規表現チートシート](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://yoshikawaweb.com/w/wp-content/uploads/regex-cheat-sheet.pdf)

[TOC]

## 
| Syntax | Example | match  | non-match |
| ------ | ------- | ------ | --------- |
| ^      | ^r      | rabbit | parrot    |
| $      | t$      | rabbit | trap      |
| \A     | ^r      | rabbit | parrot    |

## Table
| Syntax |            Example            | Syntax  |            Example            |
| :----: | :---------------------------: | :-----: | :---------------------------: |
|   .    |       任意の1文字に一致       |    a    |           a に一致            |
|   a*   |  a が0個以上に一致(最長一致)  |   a*?   |  a が0個以上に一致(最短一致)  |
|   a+   |  a が1個以上に一致(最長一致)  |   a+?   |  a が1個以上に一致(最短一致)  |
|   a?   | a が0個か1個に一致(最長一致)  |   a??   | a が0個か1個に一致(最短一致)  |
|   ^a   |    文字列の先頭の a に一致    |   a$    |    文字列の末尾の a に一致    |
|  a{3}  |          aaa に一致           |
| a{1,3} | a が1~3個連続に一致(最長一致) | a{1,3}? | a が1~3個連続に一致(最短一致) |
| a{1,}  |  a が1個以上に一致(最長一致)  | a{1,}?  |  a が1個以上に一致(最短一致)  |

| Syntax |                   Example                    | Syntax |           Example           |
| :----: | :------------------------------------------: | :----: | :-------------------------: |
|   \s   | 空白文字(改行、復帰、タブ、スペース等)に一致 |   \S   | \s に一致するもの以外に一致 |
|   \n   |                  改行に一致                  |   \r   |         復帰に一致          |
|   \t   |                  タブに一致                  |   \v   |         垂直タブに一致          |
|   \f   |                  改ページに一致                  |

|   Syntax    |             Example              | Syntax  |              Example               |
| :---------: | :------------------------------: | :-----: | :--------------------------------: |
|    [abc]    |        a or b or c に一致        | [^abc]  |       a or b or c 以外に一致       |
| [abc\|def]  |        abc or def に一致         |   $1    |  1番目にキャプチャしたものを展開   |
|    (abc)    | abc をグループ化(キャプチャする) | (?:abc) | abc をグループ化(キャプチャしない) |
|    [0-9]    |          半角数字に一致          | [-0-9]  |      半角数字かハイフンに一致      |
| [0-9A-Za-z] |         半角英数字に一致         |