Here is a **pure, clean Docker commands block** you can paste directly at the end of your README.

---

# 🐳 **Additional Docker Commands (Extra Useful Commands)**

*(Added as you requested — simple format, clean meaning)*

### **Basic Docker Commands**

* `docker ps` – Show running containers
* `docker ps -a` – Show all containers
* `docker ps -aq` – Only container IDs
* `docker images` – List all images
* `docker pull <image>` – Download image from Docker Hub
* `docker run <image>` – Run a container
* `docker run -it <image>` – Run container interactively
* `docker run -d <image>` – Run container in background
* `docker run -d -p <host>:<container> <image>` – Run container with port mapping

---

### **Useful Run Options**

* `docker run --name myapp <image>` – Give container a name
* `docker run -v vol1:/data <image>` – Attach a volume to container
* `docker run --network app-net <image>` – Attach container to a network
* `docker run -e KEY=value <image>` – Pass environment variables

---

### **Container Management**

* `docker start <id>` – Start a stopped container
* `docker stop <id>` – Stop a container
* `docker restart <id>` – Restart a container
* `docker kill <id>` – Force stop a container
* `docker rm <id>` – Remove container
* `docker rm $(docker ps -aq)` – Remove ALL containers

---

### **Container Logs & Terminal Access**

* `docker logs <id>` – View logs
* `docker logs -f <id>` – Follow logs live
* `docker exec -it <id> bash` – Enter container using bash
* `docker exec -it <id> sh` – Enter container with sh (Alpine)
* `docker top <id>` – Show processes running inside container

---

### **Image Management**

* `docker build -t myapp .` – Build image from Dockerfile
* `docker build -f Dockerfile.dev -t myapp-dev .` – Build using custom Dockerfile
* `docker rmi <image_id>` – Remove image
* `docker rmi $(docker images -q)` – Remove ALL images
* `docker tag myapp:latest username/myapp:latest` – Tag image
* `docker push username/myapp:latest` – Push to Docker Hub

---

### **Docker Networks**

* `docker network ls` – List networks
* `docker network create app-net` – Create network
* `docker network inspect app-net` – View network details
* `docker network connect app-net mycontainer` – Add container to network
* `docker network disconnect app-net mycontainer` – Remove container from network

---

### **Docker Volumes**

* `docker volume ls` – List volumes
* `docker volume create mydata` – Create volume
* `docker volume inspect mydata` – Inspect volume
* `docker volume rm mydata` – Remove volume
* `docker run -v mydata:/var/lib/mysql mysql` – Use volume with MySQL

---

### **Docker Inspect & System Info**

* `docker inspect <id>` – Detailed info about container or image
* `docker port <id>` – Check mapped ports
* `docker stats` – Show live CPU, RAM, and network usage
* `docker system df` – Show docker disk usage
* `docker system prune` – Remove unused containers/images/networks
* `docker system prune -a` – Remove **everything** unused

---

### **Docker Save & Load**

* `docker save <image> > image.tar` – Save image as tar file
* `docker load < image.tar` – Load image from tar file
* `docker export <container> > file.tar` – Export container filesystem
* `docker import file.tar newimage:latest` – Import exported container

---

### **Docker Compose**

* `docker compose up` – Start services
* `docker compose up -d` – Start in background
* `docker compose down` – Stop and remove services
* `docker compose logs` – View logs for all services
* `docker compose ps` – List containers in compose project

---


Just tell me — I can generate it instantly.
