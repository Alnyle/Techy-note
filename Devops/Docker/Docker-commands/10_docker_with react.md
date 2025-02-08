

```
# This sets the base image to the latest Node.js image.

# It includes Node.js, npm, and other necessary tools.

  

FROM node:latest

  

# Creates a new group app and adds a system user app
# create a user with permissions to run the app
# -S -> create a system user
# -G -> add the user to a group
# This is done to avoid running the app as root
# If the app is run as root, any vulnerability in the app
# can be exploited to gain access to the host system
# It's a good practice to run the app as a non-root user

  

RUN groupadd app && useradd -r -g app app



# Switches the current user to app,
# ensuring that the rest of the operations are run by this non-root user for security
USER app

  

# set the working directory to /app
WORKDIR /app

  
  

COPY package*.json ./

  
# Temporarily switches back to the root user,
# as the next steps might require root privileges.
# sometimes the ownership of the files in the working directory is changed to root
# and thus the app can't access the files and throws an error -> EACCES: permission denied
# to avoid this, change the ownership of the files to the root user

USER root

  

# Changes ownership of all files in the /app directory to the app user and app group.
# This ensures that the app user will have the necessary permissions to run the app.

RUN chown -R app:app .

  

# Installs the Node.js dependencies from package.json
RUN npm install

  

COPY . .

  
  

# Tells Docker that the container will use port 5173. This port will need to be opened
# when running the container to allow access to the app (probably a Vite project).

EXPOSE 5173


# command to run the app
CMD npm run dev
```


### Explanation:

1. **`FROM node:latest`**:
    
    - This sets the base image to the latest Node.js image. It includes Node.js, npm, and other necessary tools.
2. **`RUN addgroup app && adduser -S -G app app`**:
    
    - Creates a new group `app` and adds a system user `app` to that group without creating a password (`-S` flag).
3. **`USER app`**:
    
    - Switches the current user to `app`, ensuring that the rest of the operations are run by this non-root user for security.
4. **`WORKDIR /app`**:
    
    - Sets `/app` as the working directory. Any subsequent `RUN`, `COPY`, or `CMD` instructions will operate relative to this directory.
5. **`COPY package*.json ./`**:
    
    - Copies both `package.json` and `package-lock.json` (if available) from your local machine to the `/app` directory inside the Docker container.
6. **`USER root`**:
    
    - Temporarily switches back to the root user, as the next steps might require root privileges.
7. **`RUN chown -R app:app .`**:
    
    - Changes ownership of all files in the `/app` directory to the `app` user and `app` group. This ensures that the `app` user will have the necessary permissions to run the app.
8. **`RUN npm install`**:
    
    - Installs the Node.js dependencies from `package.json`.
9. **`COPY . .`**:
    
    - Copies the remaining project files from your local machine to the `/app` directory inside the container.
10. **`EXPOSE 5173`**:
    
    - Tells Docker that the container will use port `5173`. This port will need to be opened when running the container to allow access to the app (probably a Vite project).
11. **`CMD npm run dev`**:
    
    - Defines the command to run when the container starts. Here, it's running `npm run dev`, which likely starts your development server.




Note to work use powershell (main operating shell)

```
docker run --name react-app -v "$(pwd):/app" -v /app/node_modules -p 5173:5173 react-docker
```


```
docker run -p 5173:5173 -v "$(pwd):/app" -v /app/node_modules react-docker
```