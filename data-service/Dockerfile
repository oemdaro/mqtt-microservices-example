FROM golang:1.9-alpine3.6

WORKDIR /go/src/github.com/oemdaro/mqtt-microservices/data-service

ADD . /go/src/github.com/oemdaro/mqtt-microservices/data-service

RUN apk --no-cache add --virtual deps \
  git && \
  go get -u github.com/golang/dep/cmd/dep && \
  /go/bin/dep ensure && \
  go install && \
  apk del deps

ENTRYPOINT ["/go/bin/data-service"]
