FROM php:8-apache
ADD apache/config/site.conf /etc/apache2/sites-available/
ADD apache/certs/domain_name.crt /etc/ssl/
ADD apache/certs/private.key /etc/ssl/
ADD apache/certs/chain.crt /etc/ssl/
ADD apache/certs/domain_name.crt /etc/ssl/
ADD apache/certs/vkapi.p12 /etc/ssl/
ADD apache/certs/openssl.cnf /etc/ssl/
RUN docker-php-ext-install \
	pdo_mysql \
	&& a2enmod \
	rewrite
RUN a2enmod rewrite
RUN a2enmod ssl
RUN a2dissite 000-default.conf
RUN a2ensite site.conf
