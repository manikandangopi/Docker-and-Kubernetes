# Immutable vs Mutable Infrastructure

## **Version Upgrade Types**
| Type | Description | Example |
|------|-------------|---------|
| **Mutable** | Server 1 → Upgrade / Changes / Modify existing setup | Traditional software update on the same server |
| **Immutable** | Instance 1 is replaced by Instance 2 (new deployment) | Terraform destroy and deploy a new VM |

---

## **Terminology and Examples**

| Term | Meaning (Simple Words) | Azure Example | Fresher-Friendly Analogy |
|------|------------------------|---------------|--------------------------|
| **Immutable** | Once created, you can’t change it. If you need to change, you create a new version. | - Azure Immutable Storage for blobs – once a file is written, you cannot edit or delete it until its retention period ends.<br>- Azure VM Image – once an image is created, you don’t change it; instead, you make a new image for updates. | Like a printed book – if you want to update a chapter, you have to print a new edition. |
| **Mutable** | You can change it anytime after creation. | - Azure Virtual Machine – you can change CPU, RAM, OS updates anytime.<br>- Azure Storage Blob without immutable policy – you can edit or delete files anytime. | Like a Google Doc – you can edit the same document anytime you want. |

---

## **Immutable vs Mutable in Terraform**

| Concept | Meaning in Simple Words | Example in Terraform | Azure Example |
|---------|------------------------|----------------------|---------------|
| **Immutable** | Instead of changing an existing resource, Terraform destroys the old one and creates a new one. | If you change the `vm_size` of an Azure VM in Terraform, Terraform might delete the old VM and create a new one (depending on the property). | Changing an Azure VM from `Standard_B1s` to `Standard_B2s` may recreate the VM (new resource ID). |
| **Mutable** | Terraform updates the resource in place without deleting it. | If you change a VM tag in Terraform, it will just update the existing VM instead of recreating it. | Adding a new tag like `"Environment" = "Prod"` will update the Azure VM directly. |

---

## **Terraform vs Ansible**

| Tool | Category | Purpose | Example Capabilities |
|------|----------|---------|----------------------|
| **Terraform** | IaC Tool | Infrastructure provisioning, deployment, and management | Terraform Cloud, Terraform Enterprise, Terraform Open Source |
| **Ansible** | Configuration Management | Managing existing infrastructure, application automation | Install applications, configure servers |

---

## **Key Differences**
| Feature | Terraform | Ansible |
|---------|-----------|---------|
| **Scope** | Infrastructure provisioning & management | Application & infrastructure configuration |
| **Approach** | Declarative | Procedural |
| **Supported Providers** | Multiple (Azure, AWS, GCP, VMware, etc.) | Mostly OS-level and application-level automation |
| **Environment Support** | Hybrid | Hybrid |
