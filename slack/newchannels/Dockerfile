FROM golang:1.7.5-alpine
RUN apk update && apk upgrade
RUN apk add --no-cache git openssh make
RUN git clone https://github.com/ara-ta3/slack-timeline.git /opt/timeline
RUN mkdir -p /opt/golang
ENV GOPATH=/opt/golang
RUN make -C /opt/timeline install
RUN make -C /opt/timeline build_for_local
