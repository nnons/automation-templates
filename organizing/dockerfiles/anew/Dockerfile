
FROM golang:1.13.4-alpine3.10 AS build-env
RUN apk add --no-cache --upgrade git openssh-client ca-certificates
RUN go get -v github.com/golang/dep/cmd/dep
RUN GO111MODULE=on go get -v github.com/tomnomnom/anew

FROM alpine:latest
COPY --from=build-env /go/bin/anew /usr/local/bin
ENTRYPOINT ["anew"]