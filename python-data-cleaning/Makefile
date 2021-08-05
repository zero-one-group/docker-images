DOCKERNAME=zeroonetechnology/python-data-cleaning
VERSION=20210821

build:
	docker build --no-cache -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
