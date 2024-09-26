this command for windows shell

```
docker exec -it <container-id> /bin/bash
```

To run the shell inside docker container

```
docker exec -it <docker-container-ID-or-Name> path 
```

or

```
docker container exec -it <docker-container-ID-or-Name> shellType 
```

example:

```
docker exec -it egfdh564gfd /bin/sh or /bin/bash
```

or

```
docker container exec -it d354tfergrt bash 
```
#### Alternative
### Explanation

example

```
docker run -d -p 80:80 dockerfile/nginx
```

Running `docker run -d -p 80:80 dockerfile/nginx` indeed starts an Nginx container in detached mode. Since it doesn't provide an interactive shell, accessing the files within the container while it’s running requires additional steps.

solution

 If you really need access to the files in this container while its running, your only option is to use nsinit, nsenter or lxc-attach. Have a look at [https://blog.codecentric.de/en/2014/07/enter-docker-container/](https://blog.codecentric.de/en/2014/07/enter-docker-container/) for details.

```
docker run -d -p 80:80 dockerfilePath /bin/bash
```

example:

```
docker run -it -p 80:80 dockerfile/nginx /bin/bash
```

