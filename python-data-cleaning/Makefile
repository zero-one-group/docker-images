DOCKERNAME=zeroonetechnology/python-data-cleaning
VERSION=20210509

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
