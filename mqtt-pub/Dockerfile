FROM debian:latest

RUN apt update
RUN apt install -y mosquitto-clients
COPY ./certs /etc/mosquitto/certs

EXPOSE 8883

ENTRYPOINT ["mosquitto_pub", "-h", "172.17.0.2", "-p", "8883", "-t", "/T1", "--cafile", "/etc/mosquitto/certs/mosq-ca.crt", "-u", "user", "-P", "senha", "-m"]
CMD ["autenticado_criptografado"]
