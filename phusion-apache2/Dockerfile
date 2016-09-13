FROM phusion/baseimage
RUN \

# Install apache2
  export DEBIAN_FRONTEND=noninteractive && apt -y update && apt -y upgrade \
  && apt -y install apache2 \

# Cleanup
  && apt -y autoremove && apt -y autoclean && apt -y clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/www/html/* \
  
# Add apache2 as runit service
  && mkdir /etc/service/apache2/
COPY run /etc/service/apache2/
