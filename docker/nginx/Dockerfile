FROM nginx:1.27.4-alpine

ARG PORT

WORKDIR /var/www/html

EXPOSE ${PORT}

ENTRYPOINT [ "nginx" ]

CMD [ "-g", "daemon off;" ]