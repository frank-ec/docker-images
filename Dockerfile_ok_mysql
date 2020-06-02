FROM centos:7
RUN \
	yum -y install \
	 httpd \
	 php \
	 php-cli \
	 php-common \
	 git \
	 mod_ssl \
	 openssl  
RUN echo "<?php phpinfo() ?>" > /var/www/html/hola.php

RUN git clone https://github.com/frank-ec/admision.git /var/www/html/admision

COPY ssl.conf /etc/httpd/conf.d/default.conf

COPY docker.crt /docker.crt

COPY docker.key /docker.key

EXPOSE 80 443

CMD apachectl -DFOREGROUND
