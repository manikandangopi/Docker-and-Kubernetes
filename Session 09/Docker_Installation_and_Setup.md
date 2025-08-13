	Insall Docker	
	Install Docker step by Step on linux	ubuntu linux
	Install Docker step by step on windows	windos client/server
	Install Docker-Automated script	centos
		
Docker 	community	
(company/product Enterprise)		Mirantis
		
	Application that simplifes the process of running/managaing app process	
	portable/resources friendly	
	product to launch and manage container	
	Developers use docker to developing and deploy the app as a container image	
		
Pre-requst		
Ubuntu	64-bit linux installation	we have 24.04.02
	kernel version 3.10 higher	uname -r
	apt update	to update the packages of machines server
	apt install apt-transport-https	package manager-https based tranfser of files, data and information
	curl	command line browser
	ca-certificates	for system to check/validate the security certificates
	software-properties-common	To add /allow execution of scripts
		
Docker installation via apt repository		
Docker installation via apt repository	# Add Docker's official GPG key:	
	sudo apt-get update	to install the system local packages list 
	sudo apt-get install ca-certificates curl	"ca-certificates- https based tranfser of files, data information validate ssl certifacates
curl- command line tool to fetch data from urls."
	sudo install -m 0755 -d /etc/apt/keyrings	"/etc/apt/keyrings with:
-m 0755 - permission: owner can read/wirte/execute , other can read and write
this directory stores trusted gpg keys for verifying packages"
	sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc	download public gpg sisgining key
	sudo chmod a+r /etc/apt/keyrings/docker.asc	gives all users read only access to gpg key
		
	# Add the repository to Apt sources:	
	echo \	
	  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \	"deb- tell apt this is debian/ubuntu binary repository
arch=$(dpkg --print-architecture) → Ensures apt only downloads packages for your CPU architecture (e.g., amd64, arm64).

signed-by=/etc/apt/keyrings/docker.asc → Ensures only packages signed by Docker’s GPG key are trusted.
https://download.docker.com/linux/ubuntu → URL of Docker’s official package repo.
$(. /etc/os-release && echo ""${UBUNTU_CODENAME:-$VERSION_CODENAME}"") → Inserts your Ubuntu codename (e.g., jammy, focal) dynamically.
stable → The channel for stable Docker releases."
	  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \	
	  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null	
	sudo apt-get update	update of repo
		
Install the Docker packages.		
Install the Docker packages.	sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin	
	Package Name	Purpose / What It Does
	docker-ce	Docker Community Edition — the main Docker engine that runs containers.
	docker-ce-cli	Command-Line Interface to control Docker (docker run, docker ps, etc.).
	containerd.io	Low-level container runtime used by Docker to manage containers.
	docker-buildx-plugin	Advanced image builder supporting multi-platform builds.
	docker-compose-plugin	Runs multi-container applications defined in one YAML file.
to check status of docker	systemctl status docker	to check status of docker
to enable docker	systemctl enable docker	to enable docker
to check docker version	docker version	to check docker version
<img width="1147" height="1400" alt="image" src="https://github.com/user-attachments/assets/7ae3e7f4-eef5-4d24-9498-a475dbb907cb" />

