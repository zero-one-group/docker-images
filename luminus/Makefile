DOCKERNAME=zeroonetechnology/luminus
VERSION=20201121

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
