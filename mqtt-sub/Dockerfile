FROM debian:latest

RUN apt update
RUN apt install -y mosquitto-clients

COPY ./certs /etc/mosquitto/certs

EXPOSE 8883

ENTRYPOINT ["mosquitto_sub", "-h", "172.17.0.2", "-t", "/T1", "-v", "--cafile", "/etc/mosquitto/certs/mosq-ca.crt", "-p", "8883"]
CMD ["-u", "user", "-P", "senha"]
