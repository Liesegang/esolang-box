FROM esolang/python2

ENV BUILD_PACKAGES="recode" \
    RUNTIME_PACKAGES=""

RUN apk add $BUILD_PACKAGES $RUNTIME_PACKAGES && \
    curl -m $TIMEOUT "https://esolangs.org/wiki/Aubergine/aubergine.py" -L | awk -F "</?pre>" '{print $2}' RS="b\bb" | recode HTML..u8 > ~/aubergine.py && \
    apk del $BUILD_PACKAGES && \
    rm -rf /var/cache/apk/* /tmp/* && \
    ln -s /bin/script /bin/aubergine && \
    rm /bin/python2

COPY script /root/script
