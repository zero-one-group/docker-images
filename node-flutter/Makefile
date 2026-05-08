DOCKERNAME=01group/node-flutter
VERSION=3.41.6-3

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
