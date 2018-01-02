FROM alpine:3.5
MAINTAINER David Audet <david.audet@ca.com>

LABEL Description="Eclipse Mosquitto MQTT Broker"

RUN apk --no-cache add mosquitto
RUN mkdir -p /mosquitto/config /mosquitto/data /mosquitto/log
RUN cp /etc/mosquitto/mosquitto.conf /mosquitto/config
RUN chown -R mosquitto:mosquitto /mosquitto

COPY docker-entrypoint.sh /
#ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
