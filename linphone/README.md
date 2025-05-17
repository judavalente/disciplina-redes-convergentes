# Atividade de criação de um container com linphone

Comandos para rodar o container:

```bash
sudo docker build -t judavalente/linphone
xhost +
docker run -it --rm --name linphone -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix linphone
```
