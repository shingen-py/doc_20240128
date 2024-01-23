# Python, Django, Pandasを用いた気象データ分析結果のWeb公開

## 教材概要
この教材では、PythonのWebフレームワークであるDjangoを使って、Pandasで分析した山梨県の気象データをWeb上で公開する方法を学びます。教材は、Webサイトの設定、データのインポート、データの表示の3つの部分に分かれています。

## 教材テキスト
1. Djangoで新しいWebサイトを作成します。これには、Djangoの管理コマンドを使用します。
2. Djangoのデータベースに、Pandasで分析したデータをインポートします。このために、DjangoのORMを使用します。
3. Djangoのビューとテンプレートを使用して、インポートしたデータをWebページ上に表示します。

## サンプルコード
```python
# Djangoの管理コマンドで新しいWebサイトを作成
django-admin startproject mysite

## 作業手順
1. Django Web アプリケーションの作成
2. `mysite/mysite/models.py`に`WeatherData`モデルを追加します。
3. `python manage.py makemigrations`と`python manage.py migrate`を実行してデータベースにテーブルを作ります。
4. Pandasで分析したデータをCSVファイル（`data.csv`）に保存します。
5. csv データから Django へデータをインポートする。
6. `mysite/mysite/views.py`に`weather_view`ビューを追加します。
7. `mysite/mysite/urls.py`に`weather_view`へのURLパターンを追加します。
8. `mysite/mysite/templates/weather.html`にデータを表示するためのテンプレートを作ります。
9. `python manage.py runserver`を実行してWebサイトを起動します。ブラウザで`http://localhost:8000/weather`にアクセスすると、インポートしたデータが表示されます。