#FROM golang:1.8.1-alpine
FROM abhaydiwan/golang-test:1.0.0

RUN go get github.com/micro/go-plugins/wrapper/breaker/hystrix && \
    go get github.com/afex/hystrix-go/hystrix

ENV SOURCES /go/src/github.com/abhaydiwan/GoMicro/

COPY . ${SOURCES}

RUN cd ${SOURCES}client/ && CGO_ENABLED=0 go build

ENV CONSUL_HTTP_ADDR localhost:8500

WORKDIR ${SOURCES}client/
CMD ${SOURCES}client/client
