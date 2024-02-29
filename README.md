## Summary
This repository includes a simple golang http server w/ the gin framework

Note: These steps are mostly my scratch and your mileage may vary on running these given your OS, Go, Docker

### Run Go Client Locally

configure dependencies:
* `go mod init gogin`
* `go get -u -v ./...`

running the project:
* `go run .`
* http server listens on `localhost:8889`

testing the project:
* `go test -v -cover ./...`

building the project binary:
* `go build -o app`

### Tag Commit to Trigger Actions Workflow
create tag:
* `NEWTAG=v1.0.1; git tag $NEWTAG && git push origin $NEWTAG`

delete tag:
* `DELTAG=v1.0.1; git tag -d $DELTAG && git push origin :refs/tags/$DELTAG`

### Dockerize Go Client
build & Tag container:
* `docker build -t gogin .`
* `docker tag gogin user/gogin:latest`

login to Dockerhub:
* `docker login`

push local image to Dockerhub registry
* `docker push user/gogin:latest`
