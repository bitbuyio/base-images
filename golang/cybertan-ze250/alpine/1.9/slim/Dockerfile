FROM resin/cybertan-ze250-alpine:latest

ENV GO_VERSION 1.9.4

RUN apk add --no-cache git gcc

RUN buildDeps='curl' \
	&& set -x \
	&& apk add --no-cache $buildDeps \
	&& mkdir -p /usr/local/go \
	&& curl -SLO "http://resin-packages.s3.amazonaws.com/golang/v$GO_VERSION/go$GO_VERSION.linux-alpine-i386.tar.gz" \
	&& echo "b32ef884061d818d7b11c0407109e33e8898ccff556d395ec0d23f452141c6a1  go1.9.4.linux-alpine-i386.tar.gz" | sha256sum -c - \
	&& tar -xzf "go$GO_VERSION.linux-alpine-i386.tar.gz" -C /usr/local/go --strip-components=1 \
	&& rm -f go$GO_VERSION.linux-alpine-i386.tar.gz \
	&& apk del $buildDeps

ENV GOROOT /usr/local/go
ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH

COPY go-wrapper /usr/local/bin/

CMD ["echo","'No CMD command was set in Dockerfile! Details about CMD command could be found in Dockerfile Guide section in our Docs. Here's the link: http://docs.resin.io/deployment/dockerfile"]
