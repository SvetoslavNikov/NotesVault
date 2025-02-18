```bash
docker run hello-world
```

1. The Docker client contacted the Docker daemon.
 1. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 2. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 3. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

`
```bash
#!/bin/bash
# Recap of commands for a Java Spring Boot app with Docker

# 1. Create the project directory and move into it
mkdir my-springboot-app
cd my-springboot-app

# 2. Create a basic pom.xml file (you can edit it later)
touch pom.xml

# 3. Create the standard Spring Boot directory structure
mkdir -p src/main/java/com/example/app
mkdir -p src/main/resources
mkdir -p src/test/java/com/example/app

# 4. Build the project with Maven (clean and package)
mvn clean package

# 5. Create/edit the Dockerfile
#    (This opens vim so you can write your Dockerfile content)
vim Dockerfile
# (After editing, save and exit vim)

# 6. Build the Docker image (replace 'my-springboot-app:latest' with your preferred tag)
docker build -t my-springboot-app:latest .

# 7. Log in to your Docker registry (interactive command)
docker login

# 8. Push the Docker image to your registry
docker push my-springboot-app:latest

# 9. Run the Docker container (mapping port 8080; adjust container name and ports as needed)
docker run -d --name my-springboot-container -p 8080:8080 my-springboot-app:latest

# 10. To stop the running container
docker stop my-springboot-container

# (Optionally) Remove the container after stopping
docker rm my-springboot-container
```