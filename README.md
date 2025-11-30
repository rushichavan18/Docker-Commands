# Docker-Commands

1. System & Package Management

sudo apt-get update
Update package index from Ubuntu repositories.

sudo apt clean
Remove downloaded .deb cache to free disk space.

df -Th
Show disk usage with type and human-readable sizes.

free -h
Show RAM and swap usage with human-readable format.

clear
Clear terminal screen.

top
Real-time CPU/Memory/Process monitoring.

htop
Advanced version of top with colors (if installed).

date
Display current date/time.

env
Show all environment variables.

✅ 2. Docker Installation & Service Commands

sudo apt-get install docker.io
Install the Docker engine.

docker --version
Check Docker version.

sudo systemctl status docker
Check Docker service status.

sudo systemctl restart docker
Restart Docker daemon.

✅ 3. Docker Container Commands

docker ps
List running containers.

docker ps -a
List all containers (running + stopped).

docker ps -aq
List container IDs only.

docker run -it ubuntu
Start an interactive Ubuntu container.

docker run -it nginx
Start an interactive nginx container.

docker run -d -p 80:80 nginx
Run nginx detached, expose port 80.

docker run -d -p 81:80 nginx
Run nginx on host 81 → container 80.

docker stop <id>
Stop a container.

docker start <id>
Start a stopped container.

docker restart <id>
Restart container.

docker rm <id>
Remove a container.

docker rm $(docker ps -aq)
Remove all containers.

docker logs <container_id>
View logs of a container.

docker exec -it <id> bash
Enter container shell.

docker stats
Show CPU/memory/live usage of containers.

✅ 4. Docker Image Commands

docker images
List all images.

docker images -aq
Image IDs only.

docker rmi <image_id>
Remove an image.

docker build -t my-java-app:latest .
Build Java app Docker image.

docker build -f Docker-multi-stage -t python-app-mini .
Build Docker image using specific Dockerfile.

docker image tag python-app-mini:latest rushichavan/python-app:latest
Tag an image for Docker Hub.

docker pull mysql
Download MySQL latest image.

✅ 5. Docker Run For Applications
Java App

docker run -d -p 8000:8000 --name java-app my-java-app:latest
Run Java container exposing port 8000.

Portfolio App

docker run -d -p 3000:3000 --name portfolio portfolio-app:latest
Run React portfolio container.

Python App

docker run -d -p 80:80 python-app-mini:latest
Run Python application on port 80.

MySQL

docker run -d -e MYSQL_ROOT_PASSWORD=root mysql:latest
Run MySQL container with root password.

✅ 6. Docker Compose Commands

docker compose up
Start containers defined in compose file.

docker compose up -d
Run in background.

docker compose down
Stop and remove compose resources.

docker network ls
List docker networks.

✅ 7. Docker Volume Commands

docker volume ls
List volumes.

docker volume create mysql-data
Create MySQL volume.

docker inspect mysql-data
Inspect volume details.

✅ 8. Git Commands

git clone <repo-url>
Clone a GitHub repo.

git add .
Stage all changes.

git commit -m "message"
Commit changes.

git push
Push to GitHub.

git remote -v
Show connected remotes.

git branch -M main
Rename local branch to main.

✅ 9. File, Directory & System Management

ls, ll
List directory contents.

cd <dir>
Change directory.

rm -r <folder>
Delete a folder recursively.

cat <file>
Display file content.

watch ls
Continuously monitor file changes.

✅ 10. User & Permission Commands

cat /etc/passwd
List system users.

cat /etc/group
List system groups.

sudo usermod -aG docker $USER
Add user to Docker group.

newgrp docker
Activate docker group immediately.

sudo chown ubuntu mysql-data
Change folder ownership.

✅ 11. Memory Cache Cleaning Commands

Used to free cached memory:

sudo sync; echo 1 | sudo tee /proc/sys/vm/drop_caches
Drop page cache.

sudo sync; echo 2 | sudo tee /proc/sys/vm/drop_caches
Drop dentries & inodes.

sudo sync; echo 3 | sudo tee /proc/sys/vm/drop_caches
Drop all caches.

✅ 12. Bash History & Shell Settings

echo $HISTCONTROL
Shows history behaviour.

HISTSIZE=50000
Store 50k commands.

PROMPT_COMMAND="history -a; history -c; history -r; $PROMPT_COMMAND"
Save & reload command history automatically.

history
Show history.

⭐ BONUS SECTION — Additional Useful Commands (Not in your list)

These are extra commands I recommend for DevOps workflows:

Docker

docker inspect <container>
Show detailed container info (IP, volumes, config).

docker port <container>
Show port mappings of a container.

docker top <container>
Show processes running inside container.

docker cp <container:path> <local-path>
Copy files from container to local machine.

docker cp <local-path> <container:path>
Copy files into container.

Linux

journalctl -u docker
View Docker service logs.

uname -a
Show kernel and OS info.

uptime
Show load average + system uptime.

ps aux --sort=-%cpu
Show processes sorted by CPU usage.

du -sh *
Check folder sizes.

Git

git status
Show which files changed.

git log --oneline --graph
Pretty commit history.

git pull --rebase
Sync latest changes safely.

Networking

ip a
Show IP addresses.

sudo lsof -i :80
See which process is using port 80.

ping google.com
Test network.
