FROM ubuntu:20.04

RUN apt-get install apache2 -y

RUN sed -i 's/Listen 80/Listen 5001/' /etc/apache2/ports.conf && \
    sed -i 's/<VirtualHost \*:80>/<VirtualHost \*:5001>/' /etc/apache2/sites-enabled/000-default.conf

CMD ["apachectl", "-D", "FOREGROUND"]