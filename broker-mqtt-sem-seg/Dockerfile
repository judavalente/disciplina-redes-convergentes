FROM debian:latest

RUN apt update && \
    apt install -y mosquitto && \
    apt clean

COPY mosquitto.conf /etc/mosquitto/mosquitto.conf
EXPOSE 1883

CMD ["mosquitto", "-c", "/etc/mosquitto/mosquitto.conf"]


