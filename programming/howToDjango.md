---
title : How to django
category : Python
author : Makoto Yaugchi
---

# How to django

ここではdjangoの使い方についてお話をしていきます。djangoについては公式サイトから概要を引用させて頂きましたので、詳細については下記のリンクより参照してください。
[django](https://www.djangoproject.com/){: target="_blank" .link-dark}

>Django makes it easier to build better web apps more quickly and with less code.
Django を使用すると、より優れた Web アプリをより迅速に、より少ないコードで簡単に構築できます。

[TOC]

## django の初期設定

djangoの初期設定のコマンドです。pythonの仮想環境の構築からコマンドを書き出しています。

```
python -m venv .venv
.venv/Scripts/activate.ps1
pip install django --proxy http://**.***.*.*:****
python.exe -m pip install --upgrade pip --proxy http://**.***.*.*:****
django-admin startproject config .
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
# open in blowser http://127.0.0.1:8000/admin
# login
```

##### 上のコマンドは以下のような手順を示しています
1. 仮想環境の作成
2. 仮想環境の有効化
3. djangoのインストール
4. config という名前の project を作成
5. コマンドで migrate というものをします
6. コマンドで スーパーユーザー を作成します
7. コマンドで server を起動します
8. ブラウザで http://127.0.0.1:8000/admin にアクセスします
9. スーパーユーザー でログインします

ここまでで django の初期設定が完了しました。ロケットのサイトが表示されれば失敗なく出来ています。

## django app の作成と設計

### django アプリケーションの作成
django でアプリとなるものを作成します。コマンドを実行するとblog というフォルダができます。
この中のファイルについて作業をしていくことになります。それぞれのファイルについては順番にお話していきます。

```shell
python manage.py startapp blog
```

### models.py のモデル設計

django におけるモデルとは データベースに保存するデータのことです。
例えば blog アプリを例にすると、タイトルと本文、作者、作成日時が考えられるかもしれません。
その例として models.py を作成しています。

blog/models.py
```python
from django.db import models
from django.contrib.auth.models import User

class Post(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    author = models.CharField(max_length=200)
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title

```

#### models Fields 主な一覧
django に準備されている主な Field は以下のようになっています。基本的なところから必要に応じて拡張していけば良いでしょう。

|    Fields     | Description        |
| :-----------: | :----------------- |
|   CharField   | タイトル等の文字列 |
| IntegerField  | 数値               |
|   TextField   | テキスト           |
|   DateField   | 日付               |
| DateTimeField | 日時               |
|  EmailField   | email              |
|   UrlField    | URL                |
|   FileField   | upload files       |
|  ImageField   | image files        |

#### models Options
models class に準備されているオプションです。詳しくは下記のリンクをご参照ください。

[モデルフィールド 設定テンプレート](https://qiita.com/okoppe8/items/a1149b2be54441951de1)

|    Option    | Description        |
| :----------: | :----------------- |
| verbose_name | カラム名           |
|    blank     | ブランク           |
|     null     |                    |
|   default    | デフォルト値       |
|   editable   | フォームの表示     |
|  max_length  | 最大文字数         |
|  help_text   | ツールチップの内容 |

### views.py の設定

## 一般的な View Class

| Name         | OverView                        | Example |
| ------------ | ------------------------------- | ------- |
| View         | get(), post()などhttpメソッド用 |
| TemplateView | 代表的                          |
| ListView     | 一覧表示                        |
| DetailView   | 詳細表示                        |
| CreateView   | 作成                            |
| UpdateView   | 更新                            |
| DeleteView   | 削除                            |
| FormView     | フォーム                        |
| LoginView    | ログイン                        |
| APIView      | 外部API                         |


## TemplateView

TemplateViewの説明

## フォルダ構成(デフォルトからの変更点)

[Reference site : Django ディレクトリ構成とファイル設定](https://note.com/saito_pythonista/n/nb95c54f4c327)
```shell
<projectName>                 # project directry
├── config                   # setting
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   ├── views.py                
│   └── wsgi.py 
├── accounts                  # accounts app directry
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py             
│   ├── migrations  
│   ├── models.py
│   ├── tests.py
│   └── views.py              
├── blogs                     # blogs app
├── media                     # media files etc for user
├── QA                        # other app 
├── static                    # static files
│   ├── css
│   ├── images                # for admin
│   └── js
├── templates                 # html files
│   ├── accounts
│   ├── blogs
│   ├── QA
│   └── base.html
└── manage.py                 # manage.py
```

### Process

```shell
django-admin startproject config .
python manage.py startapp accounts
python manage.py startapp blogs
mkdir media
mkdir static
cd static
mkdir css
mkdir js
mkdir templates
cd templates
mkdir accounts
new-item urls.py
new-item forms.py
mkdir blogs
new-item urls.py
new-item forms.py
new-item base.html
```

### Setting files

1. config/urls.py
```python
from django.contrib import admin
from django.urls import path, include
from config.views import TopPageView

urlpatterns = [
   path('admin/', admin.site.urls), 
   path('', TopPageView.as_view(), name='topPage'),
   path('blogs/', include('blogs.urls')),
   path('accounts/', include('accounts.urls')),
]
```
2. config/setting.py
   1. INSTALLED_APPSの設定
   2. templatesの設定


## その他調べた使い方

### update_or_create()
[]()
```python
obj, created = Person.objects.update_or_create(
    first_name="John",
    last_name="Lennon",
    defaults={"first_name": "Bob"},
)
```