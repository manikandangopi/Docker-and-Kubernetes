# 📘 Docker Documentation — Self Learning Guide

---

## 1️⃣ What is Docker?
Docker is an open-source platform that helps you:  
- **Build**  
- **Package**  
- **Deploy**  
- **Run** applications inside lightweight, portable containers  

---

## 2️⃣ What is a Container?
A container is a **lightweight, portable unit** that packages an application with all dependencies.  
It includes:  
- Application code  
- Dependencies (libraries, environment variables, system tools)  
- Configuration files  

➡️ **Benefit:** Runs consistently across environments, independent of host details.

---

## 3️⃣ Why Use Docker?
- 🚀 **Portability** – Run anywhere (local, servers, or cloud)  
- ⚡ **Fast startup** – Containers boot in seconds  
- 🪶 **Lightweight** – Share the host kernel (no full OS per app)  
- 📦 **Dependency management** – Package all app requirements  
- 🔄 **DevOps friendly** – Integrates with CI/CD tools (Jenkins, GitLab, GitHub Actions)  

---

## 4️⃣ Virtualization vs Containerization

| Virtualization (VMs) | Containerization (Docker) |
|----------------------|---------------------------|
| Hypervisor (VMware, Hyper-V) | Docker Engine |
| Each VM runs a full OS | Containers share host OS kernel |
| Large image size (GBs) | Small image size (MBs) |
| Boot time: Minutes | Boot time: Seconds |
| Performance overhead | Near-native performance |
| Best for running full/multiple OS | Best for packaging/running apps |

---

## 5️⃣ Visual Comparison
**Virtualization:**  
- Hypervisor → VM1 = OS + App, VM2 = OS + App, VM3 = OS + App  

**Containerization:**  
- Physical Server → Host OS (Linux) → Docker Engine → Containers (App1, App2, …)  

---

## 6️⃣ Types of Hypervisors
- **Type 1 (Bare-metal):** Runs directly on hardware (VMware ESXi, Hyper-V).  
- **Type 2 (Hosted):** Runs on top of OS (VirtualBox, VMware Workstation).  

---

## 7️⃣ Type 1 vs Type 2 Hypervisors
- **Type 1:** Installed on bare metal, production use.  
- **Type 2:** Installed on OS, dev/test use.  

---

## 8️⃣ Limitations of Virtual Machines
- ⏳ Provisioning is slower than containers  
- ⚙️ Manual resource allocation  
- 🖥️ Guest OS consumes resources  
- 📉 Fewer VMs per host compared to containers  

---

## 9️⃣ Container (Detailed)
- Includes app + required libraries/binaries (not full OS).  
- Uses **Linux kernel features**:  
  - Namespaces (process, network, IPC, mount)  
  - cgroups (resource limits)  
- Virtualizes **OS** (not hardware).  
- Lightweight, portable, Docker simplifies usage.  

---

## 🔟 Container Tools
- LXC / LXD  
- CRI-O  
- containerd  
- Podman  
- Rancher  
- Docker (CE & EE)  

---

## 1️⃣1️⃣ Docker Overview
- Created in 2013 by Solomon Hykes (DotCloud).  
- Popularized DevOps container workflows.  

---

## 1️⃣2️⃣ Docker Editions
- **Community Edition (CE):** Free, open-source.  
- **Enterprise Edition (EE):** Commercial, advanced features.  

---

## 1️⃣3️⃣ Docker Platform Tools
- Docker Engine  
- Docker Desktop  
- Docker Compose  
- Docker Swarm  

---

## 1️⃣4️⃣ What is Docker Engine?
The **core runtime** that builds, runs, and manages containers.  

---

## 1️⃣5️⃣ Docker Engine Editions
- **CE:** Free, open source.  
- **EE:** Enterprise, commercial support.  

---

## 1️⃣6️⃣ Supported Platforms
- Virtual Machines (VMware, Oracle VM)  
- Cloud (AWS, Azure, GCP)  
- Hyper-V / VMware on host machines  

---

## 1️⃣7️⃣ Container Portability & Migration
- Containers are **portable images**.  
- You migrate **containers (images)**, not OS.  
- Ensure base OS compatibility (Linux vs Windows).  

---

## 1️⃣8️⃣ Applications Suitable for Docker
- Nginx  
- Tomcat  
- MySQL  
- Apache HTTP Server  
- Hadoop components (when containerized)  

---

## 1️⃣9️⃣ Docker Engine Capabilities
- Build/run containers  
- Push/pull images  
- Manage networks & volumes  
- Plugin & API support  
- Uses **containerd** runtime  

---

## 2️⃣0️⃣ Docker Desktop
All-in-one app (Windows/macOS) with:  
- Docker Engine  
- GUI  
- Docker Compose  
- Optional Kubernetes  

---

## 2️⃣1️⃣ Docker Engine vs Docker Desktop

| Docker Engine | Docker Desktop |
|---------------|----------------|
| Core runtime (Linux) | All-in-one app (Win/macOS) |
| CLI/daemon | GUI + CLI |
| Manual install | One-click install |
| Uses host resources | Built-in resource controls |
| Manual updates | Auto updates |
| Free & open-source | Free for small teams (enterprise license needed) |

---

## 2️⃣2️⃣ Docker Architecture
- **Docker Client** → CLI/API (`docker run`, `docker build`)  
- **Docker Daemon (dockerd)** → Manages containers, images, networks  
- **Docker Host** → Machine running Docker  
- **Docker Registry** → Stores images (Docker Hub/private)  

---

## 2️⃣3️⃣ Docker Components
- **Images:** Templates for containers  
- **Containers:** Running app instances  
- **Volumes:** Persistent storage  
- **Networks:** Communication drivers  

**Drivers:**  
- `bridge` → default single-host  
- `host` → use host network stack  
- `overlay` → multi-host networking  
- `none` → no networking  
- `macvlan` → assign MAC to container  

---

## 2️⃣4️⃣ Before Installing Docker Engine on Linux
- Docker Engine → Linux  
- Docker Desktop → Windows/macOS  

---

## 2️⃣5️⃣ Virtual Machine Setup (Ubuntu + VirtualBox)

### Step 1: Install VirtualBox
- Download from official Oracle website  
- Install & launch  

### Step 2: Download Ubuntu Server ISO
- Ubuntu Server **24.04.02 Live Server**  

### Step 3: Create VM
- Name: `DockerEngine-Ubuntu2402`  
- ISO: Ubuntu ISO  
- Username: `testuser`  
- Password: `*****`  
- Hostname: `dockerserver`  
- RAM: 4 GB | CPU: 3 cores | Storage: 100 GB  

### Step 4: Install Ubuntu
- Language: English  
- Network: Default  
- Proxy: None  
- Disk: Use entire disk  
- Enable SSH  

### Step 5: Post-Install
Reboot VM → Login → Switch to root:
```bash
sudo -i

