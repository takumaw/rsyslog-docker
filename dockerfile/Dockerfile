FROM debian:stretch

RUN set -ex \
    && apt-get update -y \
    && apt-get install -y \
        rsyslog \
    && apt-get clean

RUN mkdir -p /var/log/remote
ADD etc/rsyslog.conf /etc/
ADD etc/rsyslog.d/00-remote.conf /etc/rsyslog.d/

EXPOSE 514
EXPOSE 514/udp
VOLUME ["/var/log"]

CMD ["rsyslogd", "-n"]
