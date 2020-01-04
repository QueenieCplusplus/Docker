# Docker
容器管理工具

1. install docker for mac & sign up an account 

   https://hub.docker.com/r/queens/cheers2019

2. git clone https://github.com/docker/doodle.git

3. ~$ cd doodle/cheers2019

# Build 組建

4.  cheers2019$ docker build -t doodle/cheers2019 .

    容器能夠解決軟體移植和程式間去耦合性的問題，並且能全權控制容器，包含容器對資源消耗的限制。



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
>>>

        Namespace/Repository: ID
           queens/cheers2019:latest 
         (Company/AppName: version)
    
# Runtime, 運行
    
5. cheers2019$ docker run -it --rm queens/cheers2019

   透過容器技術的封裝，藉此移植應用程式於跨平台上運行。

# Ship, 移植

6. cheers2019$ docker login

7. cheers2019$ docker push queens/cheers2019 // target

          The push refers to repository [docker.io/queens/cheers2019]
          
          4092464d0de4: Pushed (12 碼)
          
          latest: digest: sha256:6fbe80f193
          
# Deploy, 部署

8. cheers2019$ docker run -d -p 80:80 --name <appname>







    
    
    
