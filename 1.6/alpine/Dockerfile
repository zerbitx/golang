FROM alpine:3.4

RUN apk add --no-cache ca-certificates

RUN set -ex \
	&& apk add --no-cache --virtual .build-deps \
		openssl \
    wget

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH

RUN apk add --no-cache \
  git \
  go \ 
  && wget -qO - https://glide.sh/get | sh \
	&& apk del .build-deps
