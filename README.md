# Docker untuk execute Spring Boot apps

using openjdk


build: 
docker build -t local-springboot-service:0.0.1 -f Dockerfile.springboot .


run example: 


docker start --name=springboot-service -v /home/build/jarplace:/usr/src/myapp/ -p 8081:8080 -e JARNAME='yourapp.jar' local-springboot-service:0.0.1



