
- Application inside container runs in an isolated network
- This allow us to run the same app running on the same port multiple times

- We need to expose the container port to the host (the machine the container runs on)

- port binding: binding the container's port the host's port to make the service available to the outside world


bind command when creating the container specify port on host with the port on the container that you want to bind

in another
let the application that run inside the container on port XXX (80 may your application run this) bind with port on my host XXX(for example port 9000) 

To bind a port on your host machine to a port inside a Docker container, you can use Docker's port mapping feature. This is usually done by specifying the `-p` or `--publish` option when running a Docker container. Here's how you can do it:

### Docker Command

```
docker run -p 9000:80 <image-name>
```

### Explanation:

- **9000**: This is the port on your host machine. You can change this to whatever port you want to use on your host.
- **80**: This is the port inside the container that your application is running on. You should change this to the appropriate port if your application is not running on port 80 inside the container.
- **image-name**: Replace this with the name of your Docker image.

### Example

If your application runs on port 3000 inside the container, and you want to bind it to port 9000 on your host, the command would be:

```
docker run -p 9000:3000 <image-name>
```

This setup allows you to access your application by visiting `http://localhost:9000` on your host machine. Docker will forward requests from port 9000 on your host to port 3000 inside the container.