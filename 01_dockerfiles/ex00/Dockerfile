#docker build -f /path/to/a/Dockerfile
#You use the -f flag with docker build to point to a Dockerfile anywhere in your file system. 
#docker build -t vim-image .
# docker run --rm -it vim-image
FROM alpine:latest
RUN apk update && apk upgrade && apk add vim
CMD ["vim"]