FROM keymetrics/index:10-alpine
RUN apk update && apk upgrade && \
  apk add --no-cache \
    bash \
    git \
    curl \
    openssh

RUN mkdir -p /usr/src/apps
WORKDIR /usr/src/apps
COPY package*.json ./
RUN npm cache clean --force
RUN npm install
COPY . .
EXPOSE 3000
CMD [ "index-runtime", "start", "index.json", "--env", "production"]