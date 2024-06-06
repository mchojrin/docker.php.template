FROM $BASE_IMG 

LABEL authors="$TU_NOMBRE <$TU_EMAIL>"

COPY app/ /var/www/html/

ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN a2enmod $APACHE_MODULES && \
	install-php-extensions $EXTENSIONES_PHP xdebug-$VERSION_XDEBUG && \
    	usermod -u 1000 www-data && \
    	groupmod -g 1000 www-data && \
	chown -R www-data:www-data /var/www/html
