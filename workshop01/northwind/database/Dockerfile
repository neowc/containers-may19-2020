FROM mysql:5.7

# set Mysql the root password to changeit
ENV MYSQL_ROOT_PASSWORD=changeit

# Write one or more Docker command to copy the *.sql into /docker-entrypoint-initdb.d
ADD 0-northwind-default-current-timestamp.sql /docker-entrypoint-initdb.d
ADD 1-northwind-data.sql /docker-entrypoint-initdb.d

# add healthcheck - v2
HEALTHCHECK --interval=30s --timeout=30s --start-period=15s --retries=3 \
        CMD mysqladmin ping -uroot -p${MYSQL_ROOT_PASSWORD}} || exit 1

# where MySQL stores the database
VOLUME /var/lib/mysql