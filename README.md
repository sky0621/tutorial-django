# tutorial-django

## setup
<pre>
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install django==1.11.7
$ python -m django --version
1.11.7
</pre>

## admin
<pre>
$ django-admin startproject mysite
$ la -R mysite/
mysite/:
合計 16K
-rwxr-xr-x 1 koge koge  804  7月  9 04:12 manage.py
drwxr-xr-x 2 koge koge 4.0K  7月  9 04:12 mysite

mysite/mysite:
合計 20K
-rw-r--r-- 1 koge koge    0  7月  9 04:12 __init__.py
-rw-r--r-- 1 koge koge 3.1K  7月  9 04:12 settings.py
-rw-r--r-- 1 koge koge  763  7月  9 04:12 urls.py
-rw-r--r-- 1 koge koge  390  7月  9 04:12 wsgi.py

$ cd mysite/
$ python manage.py runserver
</pre>

browse http://localhost:8000/

### create super user
<pre>
$ python manage.py createsuperuser
</pre>

## start app
<pre>
$ pwd
/work/src/python/github.com/sky0621/tutorial-django/mysite
$ python manage.py startapp polls
$ la polls/
合計 32K
-rw-r--r-- 1 koge koge    0  7月  9 04:38 __init__.py
-rw-r--r-- 1 koge koge   63  7月  9 04:38 admin.py
-rw-r--r-- 1 koge koge   85  7月  9 04:38 apps.py
drwxr-xr-x 2 koge koge 4.0K  7月  9 04:38 migrations
-rw-r--r-- 1 koge koge   57  7月  9 04:38 models.py
-rw-r--r-- 1 koge koge   60  7月  9 04:38 tests.py
-rw-r--r-- 1 koge koge   63  7月  9 04:38 views.py
</pre>
<pre>
$ python manage.py runserver
</pre>

browse http://localhost:8000/polls/

## migration

### SQLite3 migrate
<pre>
$ python manage.py migrate
</pre>

### modelクラスの定義からマイグレーションファイルを生成
<pre>
$ python manage.py makemigrations polls
$ la polls/migrations/
合計 16K
-rw-r--r-- 1 koge koge 1.3K  7月  9 15:40 0001_initial.py
</pre>

### マイグレーションした場合にどうなるかを（実DBに適用せず）標準出力
<pre>
$ python manage.py sqlmigrate polls 0001
</pre>

### マイグレーション実行
<pre>
$ python manage.py migrate
</pre>
