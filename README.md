1. System & Package Management
Command	Explanation
sudo apt-get update	Update package list from Ubuntu repositories.
sudo apt clean	Remove cached .deb files to free space.
df -Th	Show disk usage with filesystem type.
free -h	Show RAM and swap usage.
clear	Clear terminal screen.
top	Real-time CPU & memory usage.
htop	Colorful version of top (if installed).
env	Show environment variables.
date	Display date and time.
2. Docker Installation & Service
Command	Explanation
sudo apt-get install docker.io	Install Docker engine.
docker --version	Check Docker version.
sudo systemctl status docker	Show Docker service status.
sudo systemctl restart docker	Restart Docker service.
3. Docker Container Commands
Command	Explanation
docker ps	List running containers.
docker ps -a	List all containers.
docker ps -aq	List only container IDs.
docker run -it ubuntu	Run Ubuntu interactively.
docker run -it nginx	Run Nginx interactively.
docker run -d -p 80:80 nginx	Run Nginx detached on port 80.
docker run -d -p 81:80 nginx	Map host 81 → container 80.
docker stop <id>	Stop a running container.
docker start <id>	Start a container.
docker restart <id>	Restart a container.
docker rm <id>	Remove a container.
docker rm $(docker ps -aq)	Remove all containers.
docker logs <id>	View container logs.
docker exec -it <id> bash	Open shell inside container.
docker stats	Show CPU/RAM usage for containers.
4. Docker Image Commands
Command	Explanation
docker images	List all images.
docker rmi <image>	Remove image.
docker build -t my-app .	Build image from Dockerfile.
docker build -f Docker-multi-stage -t python-app-mini .	Build using custom file.
docker image tag local:latest username/repo:latest	Tag image for Docker Hub.
docker pull mysql	Pull MySQL image.
5. Running Applications in Docker
Java App
docker run -d -p 8000:8000 --name java-app my-java-app:latest

React Portfolio App
docker run -d -p 3000:3000 --name portfolio portfolio-app:latest

Python App
docker run -d -p 80:80 python-app-mini:latest

MySQL Database
docker run -d -e MYSQL_ROOT_PASSWORD=root mysql:latest

6. Docker Compose
Command	Explanation
docker compose up	Start services.
docker compose up -d	Start in background.
docker compose down	Stop & remove services.
docker network ls	Show networks.
7. Docker Volumes
Command	Explanation
docker volume ls	List volumes.
docker volume create mysql-data	Create volume.
docker inspect mysql-data	Show volume details.
8. Git Commands
Command	Explanation
git clone <url>	Clone a repository.
git add .	Stage all files.
git commit -m "message"	Commit changes.
git push	Push code to GitHub.
git remote -v	Show remotes.
git branch -M main	Rename local branch to main.
git status	Show modified files.
9. File & Directory Commands
Command	Explanation
ls, ll	List files (short/long).
cd <dir>	Enter directory.
cd ..	Go back one folder.
rm -r <folder>	Remove folder fully.
cat <file>	Display file content.
watch ls	Auto-refresh folder contents.
10. User & Permissions
Command	Explanation
cat /etc/passwd	List system users.
cat /etc/group	List groups.
sudo usermod -aG docker $USER	Add user to Docker group.
newgrp docker	Apply group changes.
sudo chown ubuntu mysql-data	Change ownership.
11. Memory Cache Cleanup (Linux)
Command	Explanation
sudo sync; echo 1 > /proc/sys/vm/drop_caches	Clear page cache.
sudo sync; echo 2 > /proc/sys/vm/drop_caches	Clear dentries & inodes.
sudo sync; echo 3 > /proc/sys/vm/drop_caches	Clear all caches.
12. Bash History Settings
Command	Explanation
echo $HISTCONTROL	Show history rules.
HISTSIZE=50000	Store 50k commands.
HISTFILESIZE=50000	Save 50k commands.
history	Show command history.
PROMPT_COMMAND="history -a; history -c; history -r; $PROMPT_COMMAND"	Save/load history automatically.
⭐ Bonus: Extra Useful DevOps Commands
Docker

docker inspect <container> — Detailed info (IP, ports, volumes)

docker top <container> — Processes running inside

docker cp container:/path local/ — Copy files from container

docker port <container> — Show port mappings

Linux

uname -a — Kernel & OS info

uptime — Load averages

du -sh * — Folder sizes

journalctl -u docker — Docker daemon logs

Git

git log --oneline --graph — Visual commit history

git pull --rebase — Cleanly pull latest code

Networking

ip a — Show network interfaces

sudo lsof -i :80 — Check what uses port 80

ping google.com — Connectivity test
