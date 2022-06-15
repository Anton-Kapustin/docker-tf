FROM php:8-apache
COPY ./config/site.conf /etc/apache2/sites-available/
COPY ./certs/domain_name.crt /etc/ssl/
COPY ./certs/private.key /etc/ssl/
COPY ./certs/chain.crt /etc/ssl/
COPY ./certs/domain_name.crt /etc/ssl/
COPY ./certs/vkapi.p12 /etc/ssl/
COPY ./certs/openssl.cnf /etc/ssl/
RUN docker-php-ext-install \
	pdo_mysql \
	&& a2enmod \
	rewrite
RUN a2enmod rewrite
RUN a2enmod ssl
RUN a2dissite 000-default.conf
RUN a2ensite site.conf
