FROM golang:1.7.5-alpine
RUN apk update && apk upgrade
RUN apk add --no-cache git openssh make
RUN mkdir -p /opt/golang
ENV GOPATH=/opt/golang
RUN go get github.com/ara-ta3/slack-timeline
RUN make -C /opt/golang/src/github.com/ara-ta3/slack-timeline install
RUN make -C /opt/golang/src/github.com/ara-ta3/slack-timeline build_for_local
RUN ln -s /opt/golang/src/github.com/ara-ta3/slack-timeline/slack-timeline /opt/timeline
