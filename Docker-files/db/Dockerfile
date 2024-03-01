FROM MYSQL:8.0.33
LABEL "PROJECT" = "vprofile"
LABEL  "Author" = "Rockson"


ENV MYSQL_ROOT_PASSWORD = "mysqlpass"

ENV MYSQL_DATABASE = "accounts"

ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql