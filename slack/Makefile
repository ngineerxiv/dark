DOCKER=$(shell which docker)

credentials_dir=

up:
	env CREDENTIALS=$(credentials_dir) docker-compose up

build/all:
	$(MAKE) -C newchannels build
	$(MAKE) -C timeline build

run:
	$(DOCKER) run \
		-d slack_newchannels \
		-v $(credentials_dir):/credentials \
		-c 256 \
		/opt/newchannels/newchannels -c /credentials/slack-new-channel.config
	$(DOCKER) run \
		-d slack_timeline \
		-v $(credentials_dir):/credentials \
		-v /tmp:/tmp \
		-c 256 \
		/opt/timeline -c /credentials/slack-timeline.config -db /tmp/slacktimelinedb
