---
title : How to html
category : Programming
author : Makoto Yaugchi
---

# How to html

htmlの基本構造を知り、どこに何を書けばいいのかを整理していきます。

## Html の基本の構造

base.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    
    <!-- meta -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- title -->
    <title>Document</title>

    <!-- css -->
    <script></script>

</head>

<body>
    <!-- body header -->
    <header>
        <nav>

        </nav>
    </header>
    
    <!-- body main -->
    <main>
        <p></p>
        <ul>
            <li></li>
            <li></li>
        </ul>
        <ol>
            <li></li>
            <li></li>
        </ol>
    </main>
    
    <!-- body footer -->
    <footer>

    </footer>
    
    <!-- js -->
    <script></script>

</body>
</html>
```

## どこに何を書くか

### head tag
ヘッドタグには、htmlファイルに関する情報をまとめて記述する

#### meta tag
メタタグにはhtmlの基本情報を書いておく
- 文字コード

#### title tag
ブラウザのタブに表示される文字を書く

#### script tag
cssに関する情報を書く

### body tag
ボディータグにはメインの情報を記述する

#### header tag
例としてnavbarを記述するなど、常に上部に書くヘッダー部を書く

#### main tag
サイトの情報のメインの部分を書き、主に編集するのはこの部分になる

#### footer tag
サイトの下部につけたい情報をフッターとして書く

#### script tag
上にはcssを書いたが読み込み速度を考慮し、下にjsを書くのが通例となっている


## 実際に書くとこうなる