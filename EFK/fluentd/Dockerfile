FROM fluent/fluentd:v1.16-1

# Ensure the user is root (typically, this is the default)
USER root

# Install build dependencies, install the plugin, and clean up
RUN apk add --no-cache --virtual .build-deps \
    build-base ruby-dev \
    && gem install fluent-plugin-elasticsearch \
    && gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* \
    /home/fluent/.gem/ruby/2.3.0/cache/*.gem
