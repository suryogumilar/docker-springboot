# Docker untuk execute Spring Boot apps

using jdk 18 oracle we build base image first:   
`docker build -t local-jdk18ora:0.0.1 -f Dockerfile.jdk18 .`

to run jdk 18 oracle:   
`docker run --rm -it --name tesjdk local-jdk18ora:0.0.1 /bin/bash`

build for microservice using base image created:   
`docker build -t local-springboot-service:0.0.1 -f Dockerfile.springboot .`

run example: 

obsolete:   
`docker start --name=springboot-service -v /home/build/jarplace:/usr/src/app/ -p 8081:8080 -e JARNAME='yourapp.jar' local-springboot-service:0.0.1`


`docker start --name=springboot-service -v /home/build/jarplace:/usr/src/app/ -p 8081:8080 -e RUN_SCRIPT='yourappscript.sh' local-springboot-service:0.0.1`

