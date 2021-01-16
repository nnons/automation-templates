FROM golang:1.13.4-alpine3.10 AS build-env
RUN apk add --no-cache --upgrade git openssh-client ca-certificates
RUN go get -v github.com/golang/dep/cmd/dep
RUN GO111MODULE=on go get -v github.com/projectdiscovery/chaos-client/cmd/chaos

FROM alpine:latest
COPY --from=build-env /go/bin/chaos /usr/local/bin
ENTRYPOINT ["chaos"]