DOCKERNAME=zeroonetechnology/node-firebase-tools
VERSION=20210111

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
