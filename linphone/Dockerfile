FROM ubuntu:bionic

RUN apt-get update && \     
    apt-get install -y x11-apps linphone

ENV DISPLAY=:0  

CMD ["linphone"]