FROM golang:1.7.5-alpine
RUN apk update && apk upgrade
RUN apk add --no-cache git openssh make
RUN git clone https://github.com/ara-ta3/slack-new-channel.git /opt/newchannels
RUN mkdir -p /opt/golang
ENV GOPATH=/opt/golang
RUN make -C /opt/newchannels install
RUN make -C /opt/newchannels build_for_local
