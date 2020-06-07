FROM nginx/unit:1.18.0-php7.3
RUN mkdir /www && groupadd -r wordpress && useradd --no-log-init -r -g wordpress wordpress && \
    chown -R wordpress:wordpress /www && \
    apt-get update && apt-get install --no-install-recommends --no-install-suggests -y php7.3-mysql php7.3-gd && \
    curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    cp wp-cli.phar /usr/local/bin/wpc

COPY .unit.conf.json /docker-entrypoint.d/.unit.conf.json
CMD ["unitd", "--no-daemon", "--control", "unix:/var/run/control.unit.sock"]