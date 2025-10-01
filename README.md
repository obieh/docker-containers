# Docker and containers

## A brief demonstration of dcoker and containers use case.

### What is docker?

#### Docker is a platform that uses containers to make creating, deploying, and running applications easier. A container packages an application with all its necessary parts, ensuring it runs consistently across any machine with Docker installed.


#### Here is a quick overview of its core components and how they work together:

| Component        |                             Description |
-------------------|-----------------------------------------|
| Docker Image     | A read-only template with instructions for creating a container (e.g., an ubuntu image with Apache web server)|
| Docker Conainer  | A runnable instance of an image. You can create, start, stop, or delete a container using Docker commands. |
| Dockerfile       | A text file with instructions to build a custom image. Not shown in architecture diagrams but essential. |
| Docker Client    | The primary command-line tool to interact with the Docker daemon (e.g., when you type docker run). |
| Docker Daemon    | The background service (dockerd) that builds, runs, and manages Docker containers on the host machine. |
| Docker Registry  | A service for storing and distributing Docker images (e.g., Docker Hub, or private registries). |


## Common Docker Use Cases.

#### Docker's consistency and isolation make it useful for many modern development challenges:

* Modernizing Applications: Break down large, monolithic applications into smaller, independent microservices, each running in its own container.

* Standardizing Environments: Eliminate the "it works on my machine" problem by ensuring your application runs identically on a colleague's laptop, a testing server, and a production data center.

* Streamlining CI/CD: Accelerate Continuous Integration and Continuous Delivery (CI/CD) pipelines by using containers to create consistent and ephemeral build and test environments.

* Running More Workloads: Due to their lightweight nature, Docker containers allow you to run more applications on the same hardware compared to bulkier virtual machines

## Essential Docker Commands.

### Here are some fundamental commands to get you started. The newer, object-based syntax is recommended for clarity.

| Purpose | Command (New Syntax) | Command (Old Syntax) |
|---------|----------------------|----------------------|
| Run a container from an image | docker container run <image_name> | docker run <image_name> |
| List running containers | docker container ls | docker ps |
| List all containers (including stopped) | docker container ls -a | docker ps -a |
| Stop a running container | docker container stop <container_id> | docker stop <container_id> |
| Remove a stopped container | docker container rm <container_id> | docker rm <container_id> |
| List downloaded images | docker image ls | docker images |
| Remove an image | docker image rm <image_id> | ocker rmi <image_id> |
| Build an image from a Dockerfile | docker build -t <image_name>:<tag> | (Same) |
| Pull an image from a registry | docker pull <image_name> | (Same) |
| Execute a command in a running container |docker exec -it <container_id> <command> | (same) |

## Installing Docker(Ubuntu).

1. Update your system `sudo apt update`

![](./img/Pasted%20image.png)

2. Install essential packages `sudo apt-get install ca-certificates curl gnupg` certificate authorities inclusive.

![](./img/Pasted%20image%20(2).png)

3. Create a dir for keyring with permision `sudo install -m 0755 -d /etc/apt/keyrings`

![](./img/Pasted%20image%20(3).png)

4. Download docker GPG key `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg`

![](./img/Pasted%20image%20(5).png)

5. Set permissions for all users on the Docker GPG key file within APT directory `sudo chmod a+r /etc/apt/keyrings/docker.gpg`

![](./img/Pasted%20image%20(6).png)

6. Create a Docker APT repository configuration entry for Ubuntu system `echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`

  ![](./img/Pasted%20image%20(7).png)

7. Update the syste. `sudo apt update`

![](./img/Pasted%20image%20(8).png)

8. Install latest version of docker `sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

![](./img/Pasted%20image%20(9).png)

9. Verify That docker has been installed successfully `sudo systemctl status docker`
![](./img/Pasted%20image%20(10).png)


