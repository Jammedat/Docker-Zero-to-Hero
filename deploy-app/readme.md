On App Server 1 in Stratos Datacenter create a docker compose file /opt/sysops/docker-compose.yml (should be named exactly).


The compose should deploy two services (web and DB), and each service should deploy a container as per details below:


For web service:


a. Container name must be php_host.


b. Use image php with any apache tag. Check here for more details.


c. Map php_host container's port 80 with host port 8083


d. Map php_host container's /var/www/html volume with host volume /var/www/html.


For DB service:


a. Container name must be mysql_host.


b. Use image mariadb with any tag (preferably latest). Check here for more details.


c. Map mysql_host container's port 3306 with host port 3306


d. Map mysql_host container's /var/lib/mysql volume with host volume /var/lib/mysql.


e. Set MYSQL_DATABASE=database_host and use any custom user ( except root ) with some complex password for DB connections.


After running docker-compose up you can access the app with curl command curl <server-ip or hostname>:8083/