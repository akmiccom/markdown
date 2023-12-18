---
Title : Prismjs の導入について
Category : Blog
Author : Makoto Yaguchi
---

# Prismjs の導入について
Django でwebアプリを作成しているときに、ブログの中にpythonやHTMLなどを書き込みたくなってきます。そのまま文字として入力しても味気ないので、きれいに表示できないかと検索していました。

そこで見つけたのが Prismjs です。ここでは Prismjs の Okaidia を使ってテストをしてみました。導入の方法を含めてまとめておきたいと思います。

[TOC]

## [Prism](https://prismjs.com/){: target="_blank" .link-dark} の概要
>Prism is a lightweight, extensible syntax highlighter, built with modern web standards in mind. It’s used in millions of websites, including some of those you visit daily. 

>Prismは、最新のWeb標準を念頭に置いて構築された軽量で拡張可能なシンタックスハイライターです。毎日アクセスするものを含め、何百万ものWebサイトで使用されています。

Prismのサイトより引用させていただきました。**Webサイトにコードを書くときにきれいに表示させますよ**といったものになります。私は軽量なものを期待していたのでベストマッチといったところでしょう。

## それぞれの言語におけるPrismjsの効果
今回は Prismjs の Okaidia を使ってテストをしてみました。いくつかの言語のサンプルは以下のようになっています。言語によっていろいろですね。

### Python
```python
from pprint import pprint

for i in range(2):
    pprint('aaaa')
```

### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script></script>
</head>
<body>
    <header></header>
    <main>
        <p>Hello World !!</p>
    </main>
    <footer></footer>
    <script></script>
</body>
</html>
```

### markdown
```markdown
# heading 1
- aaa
- bbb
1. aaa
2. bbb
```


### powershell
```PowerShell
for ($i=1; $i -lt 10; $i++)
{
Write-Output ($i)
} 
npm --version
npm install typescript
```


## Prismjs の使い方
Prismjsを導入するための手順を書いておきます。私も参考にした他のサイトが画像付きで詳しいサイトがありますのでそちらをご参照頂ければと思います。

1. Prismのサイトよりほしい言語に合わせて css と js を ダウンロードします
2. htmlから参照できる場所(Djangoであればstaticなど)にcssやjsの中に保存します
3. htmlのcodeタグにクラスを追加する
```html
<pre><code class="language-python">
...
</pre></code>
```
4. htmlにlinkとscriptでスタイルシートとスクリプトを追加する
```html
<!-- Prism.js -->
<link rel="stylesheet" href="{% static './css/prism.css' %}" />
...
<!-- Prism.js -->
<script src="{% static './js/prism.js' %}"></script>
```

以上です。保存箇所、リンクが正確であればこれでPrismjsの導入は完了です。

## 最後に
DjangoプロジェクトにPrism.jsを導入し、シンタックスハイライトを実現する手順が完了しました。コードがより見やすくなり、ブログ記事にプロフェッショナルな外観をもたらしてくれること間違いなしです。