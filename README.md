# Docker
容器管理工具

1. install

2. git clone https://github.com/docker/doodle.git

3. ~$ cd doodle/cheers2019

4.  cheers2019$ docker build -t doodle/cheers2019 .

          Usage:  docker build [OPTIONS] PATH | URL | -

          Build an image from a Dockerfile
          
>>> 

    Sending build context to Docker daemon // means docker server
    
    1.11-alpine: Pulling from library/golang // works like Git
    
    Status: Downloaded newer image for golang:1.11-alpine ---> e116d2efa2ab (6 碼)
    
    FROM golang:1.11-alpine AS builder (Company/AppName: ID)
    
    RUN apk add
    
    Resolving Middleware & Dependency
    
    WORKDIR /project
    
    COPY cheers.go 
    
    RUN CGO_ENABLED=0 GOOS=linux go build -a -ldflags '-extldflags "-static"' -o cheers cheers.go
    
    FROM scratch
    
    COPY --from=builder /project/cheers /cheers
    
    ENTRYPOINT ["/cheers"]
    
    Successfully built e17fa186f882
    
    Successfully tagged queens/cheers2019:latest
    
  

    
    
    
