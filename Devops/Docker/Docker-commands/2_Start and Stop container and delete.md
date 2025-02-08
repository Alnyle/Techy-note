
Docker run  command 

- Creates a new container 
- Doesn't re-use previous container

##### how all container have created 

```
docker ps -a
```
##### Start one or more stopped containers

```
docker start containerId
```

you stop or run a container using it's **name** or it's **ID**

```
docke stop <container-name-or-id>
```


### Name container 
using command:
```
docker run --name <container-name> -d -p 9000:80 <docker-image>
```

example:
```
docker run --name web-app -d -p 9000:80 nginx:1.27
```


#####  Stop all the container are currently running

```
docker stop $(docker ps -a -q)
```

#####  Delete docker container
you can delete docker container using container ***name*** or **ID**

using command:
```
docker rm <container-id-or-nanme>
```

example:
```
docker rm 235r49e843
```


#####  remove all stop docker containers

```
docker rm $(docker ps -a)
```

#####  Delete docker image

```
docker rmi <Image_name_or_id>
```

example:

```
docker rmi eo3k232
```

#####  Delete all docker images

```
docker rmi $(docker images -q)
```