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




