# "4. Djangoを用いたWebサイトの作成"

## 教材概要
この教材では、PythonのWebフレームワークであるDjangoを使ったWebサイトの作成について学びます。具体的には、Djangoの基本的な使い方から、テンプレートの作成、URLルーティング、データベースの操作、そして結果のWeb上での公開までを順を追って学びます。

## 教材テキスト
### Djangoを用いたWebサイトの作成

## サンプルコード
### views.py
```python
from django.shortcuts import render
from .models import WeatherData

def index(request):
    data = WeatherData.objects.all()
    return render(request, 'index.html', {'data': data})
```
### urls.py
```python
from django.urls import path
from myapp import views

urlpatterns = [
    path('', views.index, name='index'),
]

```
### models.py
```python
from django.db import models

class WeatherData(models.Model):
    date = models.DateField()
    temperature = models.FloatField()
    rainfall = models.FloatField()
```

## 作業手順
### 1. Djangoの環境設定
まずはDjangoの環境を設定します。以下のコマンドでDjangoをインストールします。
```
pip install django
```

### 2. Djangoプロジェクトの作成
次にDjangoのプロジェクトを作成します。以下のコマンドでプロジェクトを作成します。
```
django-admin startproject mysite
```

### 3. Djangoアプリケーションの作成
プロジェクト内にアプリケーションを作成します。以下のコマンドでアプリケーションを作成します。
```
python manage.py startapp myapp
```

### 4. データベースの設定
Djangoでデータベースを操作するための設定を行います。settings.pyを編集します。
今回はデフォルトのデータベースである SQLite を使用するため編集しません。
Django では PostgreSQL や MySQL などのデータベースを使用することができます。

### 5. ビューの作成
DjangoでWebページを表示するためのビューを作成します。views.pyを編集します。

### 6. URLのルーティング
URLをビューに接続します。urls.pyを編集します。

### 7. テンプレートの作成
Webページの見た目を決めるテンプレートを作成します。templatesディレクトリにhtmlファイルを作成します。

### 8. Djangoサーバーの起動
最後にDjangoのサーバーを起動して、Webサイトが正しく動作するか確認します。
```
python manage.py runserver
```