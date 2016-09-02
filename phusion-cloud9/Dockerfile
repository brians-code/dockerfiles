FROM phusion/baseimage
RUN \

# Install dependencies
  curl -L https://deb.nodesource.com/setup_6.x | bash \
  && export DEBIAN_FRONTEND=noninteractive && apt update && apt -y upgrade \
  && apt install -y nodejs build-essential python git sudo incron \
  && echo root | tee /etc/incron.allow \
  && echo "/var/www/html IN_CREATE chown $MYUSER:$MYGROUP \$@/\$#" | tee /var/spool/incron/root \

# Install cloud9 and ssh workspace
  && git clone git://github.com/c9/core.git /cloud9 && /cloud9/scripts/install-sdk.sh \
  && curl -L https://raw.githubusercontent.com/c9/install/master/install.sh | bash \

# Cleanup
  && apt -y purge --auto-remove build-essential python git \
  && apt -y autoremove && apt -y autoclean && apt -y clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/www/html/* ./setup_6.x \
  && npm cache clean \

# Add cloud9 as runit service
  && mkdir /etc/service/cloud9
COPY ./run /etc/service/cloud9/
