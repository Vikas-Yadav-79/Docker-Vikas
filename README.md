# Docker-Vikas
<h1>Three Tier Application in Docker</h1>

1. `FROM node`: This line specifies the base image for the Docker image being built. In this case, it uses the official Node.js image from Docker Hub as the base image. It provides the necessary runtime environment for running Node.js applications.
2. WORKDIR /app: This line sets the working directory inside the Docker container to /app. Any subsequent commands will be executed relative to this directory.
3. `COPY . .`: This line copies all files and directories from the current directory (where the Dockerfile resides) into the /app directory inside the Docker container. The first . represents the source directory on the host, and the second . represents the destination directory in the container.
4. `ENV MONGO_DB_USERNAME=admin` and `ENV MONGO_DB_PWD=password`: These lines set environment variables MONGO_DB_USERNAME and MONGO_DB_PWD inside the Docker container. They define the username and password to be used for MongoDB authentication. The values admin and password are assigned to these variables, respectively.
5. `RUN npm install`: This line executes the npm install command inside the Docker container. It installs the dependencies listed in the package.json file located in the /app directory. This step ensures that all required Node.js packages are installed in the container.
6. `EXPOSE 3000`: This line informs Docker that the container listens on port 3000 at runtime. It does not actually publish the port; it merely serves as documentation for users of the image.
7. `CMD ["node", "server.js"]`: This line specifies the default command to run when the Docker container starts. It defines an array where the first element is the command to execute (node) and the second element is the script or file (server.js) to run using that command. In this case, it starts the Node.js application by running the server.js file.
