FROM node:current-alpine

ARG UID
ARG GID

RUN apk --no-cache update && apk add --no-cache shadow sudo

RUN groupadd -g ${GID} container

RUN echo "admin ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/admin && chmod 0440 /etc/sudoers.d/admin

WORKDIR /app

RUN chown -R node:container .

USER node

CMD ["tail", "-f", "/dev/null"]