FROM node:18.17.1

RUN useradd -rm -d /home/Myapp -s /bin/bash -g users -u 501 hungchatbot && \
    mkdir -p /Myapp/app && \
    mkdir -p /Myapp/log && \
    mkdir -p /Myapp/share && \
    apt-get update && \
    npm i --location=global pm2

USER hungchatbot
WORKDIR /Myapp

RUN pm2 install pm2-logrotate && \

COPY --chown=hungchatbot:userz entrypoint.sh /Myapp/

ENTRYPOINT ["/Myapp/entrypoint.sh"]

