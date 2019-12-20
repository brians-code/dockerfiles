FROM briansdocker/phusion-apache2
RUN \

# Install php7
  export DEBIAN_FRONTEND=noninteractive && apt -y update && apt -y upgrade \
  && apt -y install php7.2 php7.2-cli php7.2-dev php7.2-json php7.2-odbc php7.2-pspell php7.2-soap php7.2-xml php7.2-bcmath php7.2-common php7.2-enchant php7.2-imap php7.2-ldap php7.2-opcache php7.2-readline php7.2-sqlite3 php7.2-xmlrpc php7.2-bz2 php7.2-curl php7.2-fpm php7.2-interbase php7.2-mbstring php7.2-pgsql php7.2-recode php7.2-sybase php7.2-xsl php7.2-cgi php7.2-dba php7.2-gd php7.2-intl php7.2-mysql php7.2-tidy php7.2-zip php-pear php-xdebug libapache2-mod-php7.2 \
  
# Cleanup
  && apt -y autoremove && apt -y autoclean && apt -y clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/www/html/* \
