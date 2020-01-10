# Flaskの練習

参考:[flask-tutorial](https://study-flask.readthedocs.io/ja/latest/index.html)(日本語版)

基本的なFlaskの使い方とチャットサイト??みたいなものを作ってherokuにデプロイまで行う。  
*多少バージョンが古かったりするので注意が必要

ex)  
`from flask.ext.sqlalchemy import SQLAlchemy` -> `from flask_sqlalchemy import SQLAlchemy`   

デプロイを行う際に`heroku create`をしてもリモートリポジトリができなかった。   
-> `git init`をしたところで行わないといけないand`web: gunicorn flaskr:app --log-file=-`(Procfile)も合わせて書き換え
