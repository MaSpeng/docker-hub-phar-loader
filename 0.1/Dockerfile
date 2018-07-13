FROM php:7.2-alpine

ENV PHAR_LOADER_VERSION 0.1.0

# Install build dependencies
RUN apk add --no-cache --virtual .build-deps \
    curl

RUN curl --location --show-error --silent --output /usr/local/bin/phar-loader https://github.com/MaSpeng/php-phar-loader/releases/download/"${PHAR_LOADER_VERSION}"/phar-loader.phar \
    && chmod +x /usr/local/bin/phar-loader \
    && apk del .build-deps

ENTRYPOINT ["phar-loader"]

CMD ["--help"]
