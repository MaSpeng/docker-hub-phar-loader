FROM php:7.2-cli-alpine3.7

ENV PHAR_LOADER_VERSION 0.1.1

# Install build dependencies
RUN apk add --no-cache --virtual .build-deps \
    curl=7.61.0-r0

RUN curl --location --show-error --silent --output /usr/local/bin/phar-loader "https://github.com/MaSpeng/php-phar-loader/releases/download/${PHAR_LOADER_VERSION}/phar-loader.phar" \
    && chmod +x /usr/local/bin/phar-loader

RUN apk del .build-deps

ENTRYPOINT ["phar-loader"]

CMD ["--help"]
