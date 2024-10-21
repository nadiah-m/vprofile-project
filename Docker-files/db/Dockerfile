FROM mysql:8.0.33

#mandatory
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
#optional
ENV MYSQL_DATABASE="accounts"

#when initialise fresh instance, docker will execute files in this file. Copy our sql file to this file for it to execute
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql