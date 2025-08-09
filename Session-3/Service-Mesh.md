# Service Mesh

## Overview
| Category | Details |
|----------|---------|
| **Traffic Management** | Routing, Load Balancing |
| **Monitoring / Observability** | Distributed Tracing |
| **Security** | Encryption, Authentication, RBAC |
| **Kubernetes Service Mesh** | Tools for security, reliability, observability |
| **Azure Kubernetes Service Mesh** | Azure Service Mesh is a layer for managing communication between microservices in a secure, reliable, and observable way. Azure supports open-source service mesh tools like Istio, Linkerd, and Consul on AKS. |

---

## Difference Between API Gateway and Service Mesh

| Feature | API Gateway (Example: Azure API Management) | Service Mesh (Example: Azure Service Mesh using Open Service Mesh on AKS) |
|---------|----------------------------------------------|-------------------------------------------------------------------------|
| **Main Purpose** | Handles external traffic coming into your application. | Handles internal communication between services (microservices). |
| **Traffic Direction** | Outside → Inside (Client → App) | Inside → Inside (Service A → Service B) |
| **Key Functions** | Authentication, rate limiting, request routing, caching. | Service-to-service encryption, traffic control, retries, observability. |
| **Azure Example** | Use Azure API Management to expose your web app APIs to customers with security and usage limits. | Use Open Service Mesh on AKS to secure and manage traffic between microservices in your app. |

---

## Popular Service Mesh Tools
- **Istio**
- **Linkerd**
- **HashiCorp Consul**
