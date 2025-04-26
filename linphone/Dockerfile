FROM debian:bullseye

# Atualizar pacotes e instalar dependências
RUN apt update && apt install -y \
    linphone \
    x11-apps \
    libgl1-mesa-glx \
    libx11-6 \
    libxcb1 \
    libxcomposite1 \
    libxcursor1 \
    libxdamage1 \
    libxi6 \
    libxtst6 \
    libxrandr2 \
    libxss1 \
    libxrender1 \
    libpulse0 \
    libnss3 \
    libatk1.0-0 \
    libatk-bridge2.0-0 \
    libcups2 \
    libdbus-1-3 \
    libxkbcommon0 \
    qtbase5-dev \
    qtbase5-dev-tools \
    qtchooser \
    libqt5gui5 \
    libqt5widgets5 \
    mesa-utils \
    dbus \
    && apt clean

# Iniciar o D-Bus
RUN service dbus start

# Configurar variáveis de ambiente
ENV DISPLAY=${DISPLAY}
ENV XDG_RUNTIME_DIR=/tmp/runtime-root

# Montar o socket D-Bus do host no container
VOLUME ["/run/dbus"]

# Definir ponto de entrada para o Linphone
ENTRYPOINT ["linphone"]
