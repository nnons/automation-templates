FROM golang:1.13-alpine AS build-env
RUN apk add --no-cache --upgrade git openssh-client ca-certificates
RUN go get -v github.com/golang/dep/cmd/dep
RUN GO111MODULE=on go get -v github.com/tomnomnom/waybackurls

FROM alpine:latest
COPY --from=build-env /go/bin/waybackurls /usr/local/bin
ENTRYPOINT ["waybackurls"]