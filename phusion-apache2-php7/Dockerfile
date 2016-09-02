FROM codekitchenws/phusion-apache2
RUN \

# Install php7
  export DEBIAN_FRONTEND=noninteractive && apt update && apt upgrade -y \
  && apt install -y php7.0* php-pear php-xdebug libapache2-mod-php7.0 \
  
# Cleanup
  && apt -y purge --auto-remove php7.0-snmp \
  && apt -y autoremove && apt -y autoclean && apt -y clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/www/html/* \
