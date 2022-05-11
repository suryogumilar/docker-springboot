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


### add yum repo

jika ketemu error : Failed to download metadata for repo


```bash
sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
```

jika gagal isntall via yum dengan pesan error : **'yum install fails: At least x more space needed on the / filesystem'**

`echo 'diskspacecheck=0' >> /etc/dnf/dnf.conf`

### gradle for develop springboot apps 

alternatif maven

`docker build -t local-gradle:2.14 -f Dockerfile.gradle .`