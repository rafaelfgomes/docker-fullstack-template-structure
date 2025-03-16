FROM composer:2.6.6

ARG UID
ARG GID

RUN apk --no-cache update && apk add --no-cache shadow sudo

RUN groupadd -g ${GID} container && useradd -m -u ${UID} -g container admin

RUN echo "admin ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/admin && chmod 0440 /etc/sudoers.d/admin

WORKDIR /app

RUN chown -R admin:container .

ADD ./docker/composer/entrypoint.sh /entrypoint.sh

RUN docker-php-ext-install pdo pdo_mysql

USER admin

ENTRYPOINT [ "sh", "/entrypoint.sh" ]

CMD ["tail", "-f", "/dev/null"]