FROM php:8.4-fpm-alpine

#composer コマンドを使用できるように composer公式Dockerイメージからコピーしてくる
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# apkの更新と curl をインストール
# set -ex 途中でエラーが出たら即停止させる
# apk --no -cache ... キャッシュの残さないようにしてインストール  
# docker-php-ext-install PHP拡張モジュールをインストール
# docker-php-ext-enable docker-php-ext-install 以外でインストールしたモジュールを有効化する
RUN apk --update add curl\
  && set -ex \
  && apk --no-cache add bash \
  && docker-php-ext-install pdo_mysql