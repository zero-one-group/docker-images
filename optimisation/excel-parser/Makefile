DOCKERNAME=zeroonetechnology/optimisation-excel-parser
VERSION=20201028

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
