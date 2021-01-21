FROM  mcr.microsoft.com/dotnet/core/sdk:3.1-focal as base
RUN apt-get update \
    && apt-get -y install curl dirmngr apt-transport-https lsb-release ca-certificates git \
    && curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && apt-get install -y nodejs libgomp1 \
    && npm install -g yarn

WORKDIR /src
RUN git clone https://github.com/microsoft/BotFramework-Composer.git

WORKDIR /src/BotFramework-Composer/Composer
RUN yarn
RUN yarn build

CMD ["yarn","startall"]

