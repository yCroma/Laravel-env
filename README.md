# Laravel-env

Laravelの開発環境を作る、自分用のDocker-composeフォルダを作りました。

## 動かすと作成されるもの

以下のツリーが作成されます。

```
.
├── README.md
├── docker
│   ├── nginx
│   │   └── default.conf
│   └── php
│       └── Dockerfile
├── docker-compose.yml
└── src
    └── index.php

```

## 実装されているもの

- フォルダ毎にデータベースを分けてmigrateすることができます
- マウントが遅くなってきた場合、`docker-compose.yml`のコメントアウトを外すと改善されると思います
- `.env`ファイル内の`APP_NAME`を設定することによって、複数環境を保持することができます

## 使い方

1. `.env`ファイル内のアプリ名を設定(以降はアプリ名を test と仮定する)
1. `docker-compose up -d --build`を実行
1. `docker exec -it test-app bash` でコンテナに入る

以降は、記事参照

## 記事
[Docker-composeでLaravel、Nginx、MySQLのローカル開発環境を作る](https://qiita.com/yCroma/items/bf2fe08580f332d7560b)
