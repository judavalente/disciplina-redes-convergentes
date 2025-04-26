FROM debian:latest

RUN apt update && \
    apt install -y mosquitto && \
    apt install -y net-tools openssl && \
    apt clean

COPY mosquitto.conf /etc/mosquitto/mosquitto.conf
COPY generate-CA.sh /

RUN mkdir -p /var/run/mosquitto \
             /var/lib/mosquitto \
             /var/log/mosquitto && \
    touch /var/log/mosquitto/mosquitto.log && \
    chown -R mosquitto:mosquitto /var/run/mosquitto \
                                 /var/lib/mosquitto \
                                 /var/log/mosquitto
    
RUN touch /etc/mosquitto/passwd && \
    mosquitto_passwd -b /etc/mosquitto/passwd user senha && \
    chmod +x /generate-CA.sh && \
    /generate-CA.sh && \
    mv /mqtt-server.crt /etc/mosquitto/certs/mosq-serv.crt && \
    mv /ca.crt /etc/mosquitto/certs/mosq-ca.crt && \
    mv /mqtt-server.key /etc/mosquitto/certs/mosq-serv.key && \
    chown -R mosquitto:mosquitto /etc/mosquitto/*

EXPOSE 8883


ENTRYPOINT ["mosquitto", "-c", "/etc/mosquitto/mosquitto.conf"]
