FROM mysql:8.4
ENV MYSQL_DATABASE=accounts
COPY src/main/resources/db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql

