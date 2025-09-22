# Step 2: Docker Engine Setup using Package Manager  

This document covers the installation of **Docker Engine** on an **Ubuntu Virtual Machine** using Docker’s apt package manager repository.  

---

## 1. Remove Older Versions (if any)  

| Command | Explanation |
|---------|-------------|
| `sudo apt-get remove docker docker-engine docker.io containerd runc` | Uninstalls any older versions of Docker or related components to avoid conflicts. |
| `ls -l /var/lib/docker` | Checks if Docker was previously installed (directory exists). If it shows *No such file or directory*, Docker isn’t installed yet. |

---

## 2. Update apt Index  

```bash
sudo apt-get update
Updates the apt package index with the latest package information.

3. Install Prerequisite Packages
bash
Copy code
sudo apt-get install ca-certificates curl gnupg lsb-release
Installs necessary packages:

ca-certificates → validates HTTPS connections

curl → downloads files from URLs

gnupg → manages encryption keys

lsb-release → identifies Ubuntu distribution details

4. Add Docker’s Official GPG Key
bash
Copy code
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
Creates a secure directory for storing repository keys

Downloads Docker’s official GPG key

Sets read permissions so apt can use the key

5. Add Docker Repository
bash
Copy code
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
Detects architecture (dpkg --print-architecture)

Uses Docker’s GPG key for package signing

Detects Ubuntu codename (jammy, focal, etc.)

Saves repository entry in /etc/apt/sources.list.d/docker.list

6. Install Docker Engine
bash
Copy code
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
Installs Docker Engine and related components:

docker-ce → Docker Engine (Community Edition)

docker-ce-cli → Docker CLI client

containerd.io → container runtime

docker-compose-plugin → enables Docker Compose v2

7. Verify Installation
bash
Copy code
docker --version
sudo systemctl status docker
sudo docker run hello-world
Displays the installed Docker version

Checks if Docker service is running

Runs a test container to confirm Docker works correctly

8. Install Specific Docker Version (Optional)
bash
Copy code
sudo apt-cache madison docker-ce
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io docker-compose-plugin
apt-cache madison docker-ce → lists available Docker versions

Install a specific version instead of the latest

Using MobaXterm to Login
1. Download MobaXterm
Open browser → Search MobaXterm download for Windows

Go to MobaXterm Download Page

Download Portable Edition, extract ZIP, run MobaXterm.exe as Administrator

2. Create SSH Session
Open MobaXterm → Click Session → Select SSH

Remote Host: 192.186.1.207

Port: 2223

Tick Specify Username → enter testuser

Click OK

3. Login with Password
Enter testuser password (hidden while typing)

When asked to save password → Select No

You are now logged into the VM

Troubleshooting MobaXterm Network Error
If you see a network error, it is usually because of NAT networking in VirtualBox.
NAT allows internet access but does not allow external SSH connections.

✅ Fix: Enable Port Forwarding in VirtualBox
Open VirtualBox → Select VM → Click Settings

Go to Network → Advanced → Port Forwarding

Add Rule:

Host Port: 2223

Guest Port: 22

Save changes

🔄 Reconnect via MobaXterm
Remote Host: localhost

Port: 2223

Username: testuser

Enter password → Login successful

Using Windows Command Prompt to Login
bash
Copy code
ssh -p 2222 testuser@localhost
# or
ssh -p 2222 testuser@<VM_IP>
On first login, type yes when asked for confirmation

Enter testuser password

Prompt will show:

ruby
Copy code
testuser@dockerserver:~$
Switch to Root User
bash
Copy code
sudo -i
Enter password when asked

You can now run commands without typing sudo each time
