FROM node:20

# Install dumb-init and dockerize
ENV DOCKERIZE_VERSION v0.7.0
RUN wget -O /usr/local/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.2.5/dumb-init_1.2.5_$(uname -m) \
    && chmod +x /usr/local/bin/dumb-init \
    && wget -O /usr/local/bin/dockerize.tar.gz https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-$(dpkg --print-architecture)-${DOCKERIZE_VERSION}.tar.gz \
    && tar -C /usr/local/bin -xzvf /usr/local/bin/dockerize.tar.gz \
    && rm /usr/local/bin/dockerize.tar.gz \
    && apt-get update && apt-get install -y postgresql-client-15
