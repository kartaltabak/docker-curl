FROM alpine:latest

RUN apk add curl

ARG KTVERSION_FILE="/sbin/ktversion"

RUN echo "#!/usr/bin/env sh" > $KTVERSION_FILE && \
    echo -n "echo " >> $KTVERSION_FILE && \
    echo "$(curl --version | head -1 | awk '{ print $2 }')" >> $KTVERSION_FILE && \
    chmod +x $KTVERSION_FILE

ENTRYPOINT ["curl"]
