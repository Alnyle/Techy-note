
### ********Important********

A **container** is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the **code, runtime, libraries, and dependencies**. It is based on **Docker images**, which consist of multiple **layers**.

#### **Structure of a Container:**

1. **Base Layer (Linux Base Image)**
    
    - Most images are built on **Alpine Linux** because it is lightweight (~5 MB).
    - Other common base images: Ubuntu, Debian, CentOS, etc.
2. **Intermediate Layers**
    
    - Additional dependencies, libraries, and frameworks required for the application.
    - Each command in a **Dockerfile (RUN, COPY, ADD, etc.)** creates a new layer.
3. **Application Layer**
    
    - This is the actual code of your application (e.g., Python, Node.js, Java).
    - It sits on top of all the other layers.

#### **How Layers Work in Containers?**

- **Layers are read-only**: When you create a container, a **writable layer** is added on top of the image layers.
- **Efficient storage**: Docker reuses existing layers to avoid duplication.
- **Updates & Optimizations**: If only a small part of an image changes, Docker downloads only the changed layers instead of the whole image.

Would you like an example of how layers work in a Dockerfile? 🚀

docker it **virtual tool** which mean unlike virtual machine does not have two layers where the operating systems in your machine are Isolated because every machine use it's own **kernel**  
virtual tools only have one layer which it's ***application layer*** this mean docker container instead of running on own kernel it's use **HOST OS** 

What is Containers?
- Layers of images
- Most Linux Base image (mostly alpine), because small in size
- more layer between and application and base layer
- Application image on top



###  Good Feature must know
Docker images are made up of multiple layers, and these layers are shared across containers to optimize storage and speed up downloads.

#### How It Works:

4. **First-time Download**: When you pull a Docker image for the first time, all layers of the image are downloaded and stored locally.
5. **Subsequent Pulls**: If you pull the same image again, Docker checks which layers you already have locally. It will only download new or updated layers (if the image has changed) and reuse the existing ones.
6. **Layer Caching**: When building images, Docker caches layers so that unchanged layers do not need to be rebuilt. This speeds up builds and reduces redundant downloads.

This layer-based approach makes Docker efficient in both storage and networking. 🚀

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
- it's check if image is available locally if not it's pull the image and run it

using command

```
docker run dockerimage:version
```
 
  example
  
```
docker run nginx:122-alpine
```


##### To run docker image as container without logs

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
 
 