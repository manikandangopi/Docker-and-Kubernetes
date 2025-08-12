# Docker Containerization Platform Overview

*Session 8 - 2025*

Docker Containerization platform  
Mirantis Docker Enterprise edition  
Develop, build, ship and run containers  

Without hypervisor we can deploy container in Linux kernel  

Desktop version - Linux, Windows, Mac  

Docker does not mandatorily need hypervisor  

---

## Container runtime alternatives

- Linux LXC container (application package: apps code, lib files, dependencies)  
- Rocket (Docker is a company containerization platform)  
- Podman  
- Mirantis container runtime  
- Docker is not LXC  
- Docker Engine  
- Docker is not a virtual machine solution  
- CRI-O  
- Docker is not a config management tool like Chef, Puppet, Ansible  
- Containerd  
- Docker is not a container  

---

## Docker Subcomponents

- Docker Engine = Docker Daemon + REST API + CLI (3 components will install)  
- Functions:  
  1. Managing images  
  2. Managing containers  
  3. Managing network  
  4. Managing other objects  

- Docker daemon (service) / Docker server: `dockerd`  
  - Continuously running service via systemd  
  - Builds Docker images  
- REST API: where `dockerd` is running, used to track containers and manage lifecycle  
- Docker client: Docker CLI  

---

## Docker Image

- Copy-on-write union filesystem  
- Read-only template package  
- Only changes will be written or copied to disk/repository  
- Contains OS libraries + dependencies + prerequisites + tools + scripts + application code  

---

## Docker Repository / Registry

- Docker Hub container registry  
- Image management service (SaaS app container registry) to check images, store  
- Storing, sharing/distributing, and pulling/accessing images  
- Public/private repositories (example: Azure Container Registry)  

---

## Docker Container

- Running instance of Docker image  

---

## Dockerfile

- Text document containing specifications  

---

## Docker Engine

- Docker server  
- REST API  
- Docker client  

---

## Docker Objects

- Docker object  
- Docker storage  
- Docker volume  
- Docker networks  
- Docker plugins  
- Docker service objects  
