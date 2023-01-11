FROM php:7.2.2-fpm

ARG http_proxy="http://proxy.astelit.ukr:3128"
ARG https_proxy="http://proxy.astelit.ukr:3128"

RUN echo "Acquire::http::Proxy \"$http_proxy\"; Acquire::https::Proxy \"$https_proxy\";" > /etc/apt/apt.conf.d/70proxy

RUN apt-get update && \
	apt-get install -y mysql-client && \
	docker-php-ext-install pdo_mysql

WORKDIR "/application"