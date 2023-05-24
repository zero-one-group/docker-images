DOCKERNAME=01group/node-flutter-rfc
VERSION=20230524

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
