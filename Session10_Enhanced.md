# Session 10 – Docker Commands and Usage

## Table of Contents
1. [Install Nginx in Docker Engine](#1-install-nginx-in-docker-engine)
2. [Create a Docker Hub Account](#2-create-a-docker-hub-account)
3. [Check OS Release Version of Container](#3-check-os-release-version-of-container)
4. [Add User to Docker Group](#4-add-user-to-docker-group)
5. [Install Ubuntu Container](#5-install-ubuntu-container)
6. [Pull Specific Ubuntu Version](#6-pull-specific-ubuntu-version)
7. [List All Images](#7-list-all-images)
8. [Enter a Running Container](#8-enter-a-running-container)
9. [Start a Container](#9-start-a-container)
10. [Remove a Container](#10-remove-a-container)
11. [Stop a Container](#11-stop-a-container)
12. [Save a Container as an Image](#12-save-a-container-as-an-image)
13. [Login to Docker Hub](#13-login-to-docker-hub)
14. [Tag an Image](#14-tag-an-image)
15. [Push Image to Docker Hub](#15-push-image-to-docker-hub)
16. [Common Errors & Fixes](#common-errors--fixes)
17. [Sample Outputs](#sample-outputs)

---

## 1. Install Nginx in Docker Engine
```bash
docker run -d -p 8080:80 nginx
```
**Steps:**
1. **Check Image** – Docker searches locally for the `nginx` image.  
2. **If found** → proceed.  
3. **If not found** → pull from Docker Hub.  
4. **Create Container** – An isolated container is created from the Nginx image.  
5. **Network Binding** – Maps host port `8080` → container port `80`.  
6. **Start Process** – Runs Nginx web server inside the container.  
7. **Run in Background** – `-d` keeps the process running without blocking the terminal.  

---

## 2. Create a Docker Hub Account
- Visit [https://hub.docker.com](https://hub.docker.com) and sign up.

---

## 3. Check OS Release Version of Container
```bash
cat /etc/os-release
```

---

## 4. Add User to Docker Group
```bash
getent group docker                # Check if docker group exists
sudo groupadd docker               # Create docker group (if not exists)
sudo usermod -aG docker testuser   # Add user to docker group
```
> **Note:** Log out & log back in for changes to apply.

---

## 5. Install Ubuntu Container
```bash
docker run -it ubuntu bash
```
- `-it` → interactive terminal  
- `ubuntu` → latest Ubuntu image from Docker Hub  
- `bash` → run bash shell inside container  

---

## 6. Pull Specific Ubuntu Version
```bash
docker pull ubuntu:jammy
```
- `:jammy` is the tag for the Ubuntu version.

---

## 7. List All Images
```bash
docker images
```

---

## 8. Enter a Running Container
```bash
docker exec -it <container_id_or_name> bash
```

---

## 9. Start a Container
```bash
docker start <container_id>
```

---

## 10. Remove a Container
```bash
docker rm <container_id>
```

---

## 11. Stop a Container
```bash
docker stop <container_id>
```

---

## 12. Save a Container as an Image
```bash
docker commit -m "Installed nodejs" -a "Mani" 655dc29de9b3 mechiemani/ubuntu-nodejs
```

---

## 13. Login to Docker Hub
```bash
docker login -u mechiemani
```

---

## 14. Tag an Image
```bash
docker tag mechiemani/ubuntu-nodejs linuxrepo/ubuntu-nodejs
```

---

## 15. Push Image to Docker Hub
```bash
docker push mechiemani/ubuntu-nodejs
```

---

## Common Errors & Fixes

| Error Message | Cause | Solution |
|---------------|-------|----------|
| `pull access denied for ngnix, repository does not exist` | Typo in image name (`ngnix` instead of `nginx`) | Use correct image name: `docker run nginx` |
| `permission denied while trying to connect to the Docker daemon socket` | User not in Docker group | Add user to Docker group and relogin |
| `image not found` | Image not present locally | Use `docker pull <image>` to download |
| `Error response from daemon: Conflict` | Container with same name exists | Remove old container with `docker rm` or use a different name |

---

## Sample Outputs

> Below are some example outputs for key commands. You can replace these with actual screenshots when uploading to GitHub.

**docker images**
```
REPOSITORY             TAG       IMAGE ID       CREATED          SIZE
nginx                  latest    eeb9db34b331   2 days ago       142MB
ubuntu                 jammy     5a81c4b8502e   1 week ago       77MB
```

**docker ps**
```
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                  NAMES
b7a1f5a8d1f4   nginx     "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes   0.0.0.0:8080->80/tcp   nginx-web
```

