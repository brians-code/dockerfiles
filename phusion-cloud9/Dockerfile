FROM phusion/baseimage
RUN \

# Install dependencies
  curl -L https://deb.nodesource.com/setup_6.x | bash \
  && export DEBIAN_FRONTEND=noninteractive && apt -y update && apt -y upgrade \
  && apt -y install nodejs inotify-tools build-essential python git \

# Install cloud9 and ssh workspace
  && git clone git://github.com/c9/core.git /cloud9 && /cloud9/scripts/install-sdk.sh \
  && curl -L https://raw.githubusercontent.com/c9/install/master/install.sh | bash \

# Cleanup
  && apt -y purge --auto-remove build-essential python git \
  && apt -y autoremove && apt -y autoclean && apt -y clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/www/html/* ./setup_6.x \
  && npm cache clean \

# Add runit services
COPY ./etc/service/ /etc/service/
