FROM php:8.4-fpm-alpine

#composer コマンドを使用できるように composer公式Dockerイメージからコピーしてくる
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

# apkの更新と curl をインストール
# set -ex 途中でエラーが出たら即停止させる
# apk --no -cache ... キャッシュを残さないようにしてインストール 
# docker-php-ext-install PHP拡張モジュールをインストール
# docker-php-ext-enable docker-php-ext-install 以外でインストールしたモジュールを有効化する
RUN apk --update add curl \
  && set -ex \
  && apk --no-cache add bash autoconf build-base yaml-dev linux-headers nodejs npm\
  && pecl install redis yaml apcu msgpack \
  && docker-php-ext-install pdo_mysql sockets \
  && docker-php-ext-enable redis
  