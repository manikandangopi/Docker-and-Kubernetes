# Session 7: OS-Level Virtualization vs Hardware Virtualization (Containers vs VMs)

## Overview

| OS-Level Virtualization (Containers)       | Hardware Virtualization (Virtual Machines)                |
|--------------------------------------------|------------------------------------------------------------|
| Lightweight process isolation using kernel features (namespaces, cgroups) | Full virtual machines emulating hardware with guest OS       |
| Shared kernel, isolated processes & resources | Separate kernel per VM with full OS isolation              |
| Fast startup, minimal resource overhead    | Slower startup, higher resource usage                      |

---

## Timeline & Evolution

| Year | OS-Level Virtualization                       | Hardware Virtualization                              |
|-------|----------------------------------------------|----------------------------------------------------|
| 2000  | FreeBSD Jails (early OS process isolation)   | VMware GSX Server (x86 virtualization)              |
| 2003  | Linux-VServer                                | Microsoft Virtual Server                             |
| 2005  | Solaris Zones                               | Xen 3.0 open-source hypervisor                       |
| 2007  | Google Containers (Borg cluster management)  | KVM added to Linux kernel                            |
| 2008  | LXC (Linux Containers: namespaces + cgroups) | VMware ESXi replaces ESX                             |
| 2011  | Cloud Foundry Warden (container manager)    | VMware vSphere 5.0, Microsoft Hyper-V R2            |
| 2013  | Docker popularizes container packaging       | VMware vSphere 5.5 VSAN public beta                  |
| 2014  | CoreOS rkt (security-focused runtime)       | VMware VSAN GA, Azure nested virtualization          |
| 2015  | Open Container Initiative (OCI) formed       | vSphere 6.0 with Virtual Volumes                      |
| 2016  | Windows Server Containers & Hyper-V Containers | vSphere 6.5 integrated HTML5 client                  |
| 2017  | Podman, gVisor introduced                     | Nutanix AHV, VMware Cloud on AWS                      |
| 2018  | CRI-O Kubernetes runtime (Docker-less)       | vSphere 6.7 Hybrid Linked Mode                        |
| 2019  | Docker deprecated in Kubernetes               | VMware Project Pacific (K8s integration)              |
| 2020+ | Kubernetes removes Docker runtime, Docker Shim removal | VMware Tanzu Kubernetes portfolio                   |

---

## Key Concepts & Technologies

### OS-Level Virtualization (Containers)

- **Namespaces:** Process/resource isolation.
- **cgroups:** Resource limiters (CPU, memory, I/O).
- **Runtimes:**
  - `runc`: low-level runtime launching container processes.
  - `containerd`: container lifecycle manager.
  - `CRI-O`: Kubernetes-optimized runtime.
  - `gVisor`: sandboxed runtime.
- **Standards:** OCI (Open Container Initiative).
- **Orchestration:** Kubernetes.

### Hardware Virtualization (VMs)

- Full virtual machines with separate guest OS.
- Hypervisors like VMware ESX/ESXi, KVM, Xen, Hyper-V.
- Higher overhead but stronger isolation.
- Suitable for legacy & isolated workloads.

---

## Docker and Kubernetes Ecosystem Evolution (2013–Present)

- 2013: Docker popularizes containers.
- 2015: OCI formed.
- 2016: CRI interface introduced for K8s.
- 2017: containerd extracted from Docker, Podman appears.
- 2018–2020: Kubernetes moves away from Docker runtime.
- Now: containerd, CRI-O, Podman are main runtimes.

---

## Summary Table

| Component       | Role                                         | Analogy                 |
|-----------------|----------------------------------------------|-------------------------|
| OCI             | Container runtime and image standards        | Traffic rules for containers |
| runc            | Low-level container process launcher         | Car engine              |
| containerd      | Container lifecycle manager                   | Driver                  |
| CRI-O           | Kubernetes-focused container runtime         | Taxi driver for K8s     |
| Namespaces      | Process/resource isolation                    | Separate rooms          |
| cgroups         | Resource quota management                      | Resource limits per room |
| VM Hypervisors  | Full hardware emulation and guest OS hosting | Separate houses         |

---

## References

- [Open Container Initiative (OCI)](https://opencontainers.org/)
- [Docker](https://www.docker.com/)
- [Kubernetes](https://kubernetes.io/)
- [Podman](https://podman.io/)
- [containerd](https://containerd.io/)
- [CRI-O](https://cri-o.io/)

---

*End of Session 7*

---

