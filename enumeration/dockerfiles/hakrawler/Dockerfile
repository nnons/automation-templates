FROM golang:1.12-alpine AS build-env
RUN apk add --no-cache --upgrade git openssh-client ca-certificates
RUN go get -v github.com/golang/dep/cmd/dep
RUN GO111MODULE=on go get -v github.com/hakluke/hakrawler

FROM alpine:latest
COPY --from=build-env /go/bin/hakrawler /usr/local/bin
ENTRYPOINT ["hakrawler"]