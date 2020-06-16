FROM mysql:8.0

ENV TZ=UTC \
  MYSQL_DATABASE=my_app \
  MYSQL_USER=my_app \
  MYSQL_PASSWORD=secret \
  MYSQL_ROOT_PASSWORD=secret

COPY ./my.cnf /etc/my.cnf
