FROM php:7.2-cli

RUN apt-get update

RUN apt-get install -y apache2

RUN cd /srv
RUN mkdir www
RUN cd www
RUN mkdir mediawiki
WORKDIR /srv/www/mediawiki
COPY /Resources/public/index.php .

RUN cd /etc/apache2/sites-available

COPY /Resources/wiki.conf /etc/apache2/sites-available
RUN cd ..
RUN a2ensite wiki.conf
RUN service apache2 restart