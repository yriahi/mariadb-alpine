## Description
This repo aims at creating a Docker image running MariaDB on Alpine linux. For details on how the image is built, refer to the Dockerfile in this repo. The image can be further customized with more `RUN` lines; or  any added script to the image during build time.



## Details:
- The `--datadir` used is `/var/lib/mysql`.
- Create system tables in the `--datadir` database directory by running `mysql_install_db` as  `--user=mysql`.
- Starts mysqld server as `--user=mysql` using `mysqld_safe` (MySQL Server Startup Script), which is the recommended way to start a mysqld server on Unix that doesn't have `systemd`.
- Alter `max_allowed_packet` in `/etc/mysql/my.cnf` to `max_allowed_packet = 200M` (2 lines).




##### References:
- https://wiki.alpinelinux.org/wiki/MariaDB
- https://mariadb.org/
- https://dev.mysql.com/doc/refman/5.7/en/mysqld-safe.html
