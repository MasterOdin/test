FROM phusion/baseimage:0.11

CMD ["/sbin/my_init"]

RUN apt-get update -y && apt-get install -y build-essential vpnc ruby-full libsybdb5 freetds-dev freetds-common make sshpass rsync
RUN gem install tiny_tds
# Setup vpnc service
RUN mkdir -p /etc/service/vpnc
COPY bin/vpnc.sh /etc/service/vpnc/run

# Clean up
RUN apt-get autoremove -y \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
