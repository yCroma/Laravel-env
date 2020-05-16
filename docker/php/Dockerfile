FROM php:7.4-fpm

# composer のダウンロード用
RUN apt-get update \
  && apt-get install -y zip libzip unzip \
  && docker-php-ext-install zip

# install composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# root でも composer を使えるようにする
ENV COMPOSER_ALLOW_SUPERUSER 1

# composer のインストールされるディレクトリの設定
ENV COMPOSER_HOME /composer

# グローバルインストール用のパスを通す
ENV PATH $PATH:/composer/vendor/bin

# laravel installer のインストール
RUN composer global require "laravel/installer"

# データベース用のインストール
RUN apt-get update \
  && apt-get install -y libpq-dev \
  && docker-php-ext-install pdo_mysql pdo_pgsql

# Node.js のインストール
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash - \
  && apt-get update \
  && apt-get install -y nodejs

WORKDIR /var/www/html