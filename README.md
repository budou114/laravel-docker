環境構築
1. Laravel プロジェクトの新規作成
```
docker-compose exec app composer create-project --prefer-dist laravel/laravel .
```

2. .envの修正
```
修正前
DB_CONNECTION=sqlite
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=laravel
# DB_USERNAME=root
# DB_PASSWORD=

修正後
DB_CONNECTION=mysql
DB_HOST={DBのコンテナ名}
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME={mysqlのユーザー名}
DB_PASSWORD={mysqlのパスワード}
```

3. マイグレーションコマンドの実行
```
docker-compose exec app php artisan migrate
```