# FurimaApp

## 環境構築

Docker ビルド

Git clone リンク

git clone https://github.com/yukietan/FurimaApp.git

docker-compose up -d --build

エラーになる場合 docker-compose.yml の一行目 version: '3.8' を削除
docker-compose.yml 内を以下のように編集
mysql:
image: mysql:8.0.26
platform: linux/amd64 (← この記述を追加)
environment:

## Laravel 環境構築

docker-compose exec php 　 bash

composer install

.env ファイル設定、環境変数を以下のように変更
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=laravel_user
DB_PASSWORD=laravel_pass

php artisan key:generate

php artisan migrate

## 使用技術

PHP バージョン（ホスト環境）: 8.4.5 (Mac 本体)

PHP バージョン（Docker コンテナ内）: 8.3

Laravel バージョン: 8.83.29

MySQL バージョン: 8.0.26

## ER 図

![ER図](er-furima.svg)

## URL

環境開発 : http://localhost/

phpMyAdmin : http://localhost:8080
