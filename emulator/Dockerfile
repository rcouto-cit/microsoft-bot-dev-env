FROM ubuntu:18.04

RUN apt-get update \
	&& apt-get -y install curl dirmngr apt-transport-https lsb-release ca-certificates git \
	&& curl -sL https://deb.nodesource.com/setup_10.x | bash - \
	&& apt-get install -y nodejs libgomp1 libsecret-1-dev libnss3-dev libgtk-3-0 libx11-xcb1 libxss1 libasound2 x11-apps \
	&& npm install i -g yarn lerna@3.4.0

WORKDIR /app
RUN curl -L -o BotFramework-Emulator-4.11.0 https://github.com/microsoft/BotFramework-Emulator/releases/download/v4.11.0/BotFramework-Emulator-4.11.0-linux-x86_64.AppImage
RUN chmod 700 BotFramework-Emulator-4.11.0
RUN ./BotFramework-Emulator-4.11.0 --appimage-extract

WORKDIR /app/squashfs-root

CMD ["./AppRun"]