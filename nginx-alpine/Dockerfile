FROM nginx:alpine

ENV DOCKERIZE_VERSION v0.7.0
RUN    wget -O /usr/local/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.2.5/dumb-init_1.2.5_$(uname -m) \
    && chmod +x /usr/local/bin/dumb-init \
    && LARCH=$(if [ "$(uname -m)" == "aarch64" ] ; then echo "arm64" ; elif [ "$(uname -m)" == "x86_64" ] ; then echo "amd64" ; else uname -m ; fi) \
    && wget -O /usr/local/bin/dockerize.tar.gz https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-${LARCH}-${DOCKERIZE_VERSION}.tar.gz \
    && tar -C /usr/local/bin -xzvf /usr/local/bin/dockerize.tar.gz \
    && rm /usr/local/bin/dockerize.tar.gz \
    && rm -rf /usr/share/nginx/html/*
