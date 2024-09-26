
## ********Important********

docker image is base image which mostly a light weight linux operating image that has node, npm or what ever tool your application need to run



Docker: like Virtual machine but light weight it's virtual tool. 

usually in every operating system you two layers:
- OS Kernel layer which interact directly the hardware your computer it's works as intermediate layer between your computer hardware and your application Layer
- Application Layer your applications are running

docker it **virtual tool** which mean unlike virtual machine does not have two layers where the operating systems in your machine are Isolated because every machine use it's own **kernel**  
virtual tools only have on layer which it's ***application layer*** this mean docker container instead of running on own kernel it's us **HOST OS** 


##### To see all docker image

```
docker images 
```


##### To see current running container

```
docker ps
```

##### To pull docker hub: 

```
docker pull imageName:version 
```

- real example:
```
docker pull nginx:1.27
```

#####  To run docker image as container

```
docker run imageName:version
```

- example
	`docker run nginx:1.27`

##### To run image even if not your local machine 
- it's check if image is available locally if not it's pull the image

using command

```
docker run dockerimage:version
```
 
  example
  
```
docker run nginx:122-alpine
```


##### To docker image as container without logs

run the container in background and print the container ID

```
docker run -d imageName:version
```

- example
```
docker run -d nginx:1.27
```

##### To View logs from service running inside container

```
docker logs containerImageID
```


##### Stop docker container from running

  using command
```
 docker stop containerId
```
- example
```
docker stop 324rt3f47yusdhdt673jasdfyga
```



## Delete

##### Delete docker image

 using command
 
```
docker rmi <Image-id>
```
 
 example:

```
docker rmi gdf54saq43r
```

#### Delete all docker images

 using command
 
```
docker system prune -a
```
 
 