#docker build -t go-image .
#docker run -it --rm go-image

FROM golang

COPY . /usr/src/project
WORKDIR /usr/src/project

RUN go build hello-world.go
CMD ["./hello-world"]