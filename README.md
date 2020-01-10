# Flaskの練習

参考:[flask-tutorial](https://study-flask.readthedocs.io/ja/latest/index.html)(日本語版)

基本的なFlaskの使い方とチャットサイト??みたいなものを作ってherokuにデプロイまで行う。  
*多少バージョンが古かったりするので注意が必要

ex)  
`from flask.ext.sqlalchemy import SQLAlchemy` -> `from flask_sqlalchemy import SQLAlchemy`   

デプロイを行う際に`heroku create`をしてもリモートリポジトリができなかった。   
-> `git init`をしたところで行わないといけないand`web: gunicorn flaskr:app --log-file=-`(Procfile)も合わせて書き換え

## herokuでのデプロイ方法
1. herokuに登録
2. [heroku-toolbelt](https://devcenter.heroku.com/articles/heroku-cli)で各自のOSに合わせてダウンロード
3. `$ heroku login`->ブラウザが立ち上がりログインページが出る(事前にログインしてたから？)
4. `$ pip install gunicorn`
5. Procfileを作成(.gitがあるところで)
6. Procfileに```web: gunicorn flaskr:app --log-file -```と書く->`web: guicorn [YOUR_APP_NAME]:app --log-file -`
7. `$ foreman start`->最初動かなかったので`$ sudo gem install foreman`を行なった。
8. gitでリポジトリを作成->作成済みならOK
9. `$ heroku create` -> `$ heroku create [APP_NAME]`[APP_NAME]に好きなように名前を設定できる。設定しないと適当に決めてくれる。
10. `$ git remote`でリモートリポジトリを確認してherokuリポジトリがあればOK->`$ git push heroku master`を行う。
11. `$ heroku ps:scale web=1`プロセスを変えるらしい...よくわからん
12. `$ heroku create`の時に出たURLから自分のアプリに飛べる！
13. デプロイを喜ぶ
