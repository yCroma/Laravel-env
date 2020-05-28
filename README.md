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
