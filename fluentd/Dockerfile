FROM fluent/fluentd:onbuild

USER root

RUN apk add --update --virtual .build-deps \
        sudo build-base ruby-dev \

 && sudo -u fluent gem install fluent-plugin-s3 fluent-plugin-concat \

 && sudo -u fluent gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/* \
           /home/fluent/.gem/ruby/2.3.0/cache/*.gem

USER fluent

EXPOSE 24284
