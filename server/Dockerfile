#FROM golang:1.8.1-alpine
FROM abhaydiwan/golang-test:1.0.0

RUN export GO111MODULE=on
RUN export CGO_ENABLED=0
RUN go clean -modcache



ENV SOURCES /go/src/github.com/abhaydiwan/GoMicro/

RUN cd ${SOURCES}server/ && CGO_ENABLED=0 go build

ENV CONSUL_HTTP_ADDR localhost:8500

WORKDIR ${SOURCES}server/
CMD ${SOURCES}server/server
