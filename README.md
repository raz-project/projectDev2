# projectDev2

🛠️ Automated Server Setup with Ansible
This project automates server setup using Ansible. It creates users, installs Docker, sets up the firewall, and deploys a static website inside a Dockerized NGINX container. Jenkins support is included for automated deployments.

📚 What It Does
Creates users on the server

Installs Docker and Docker Compose

Opens firewall ports for SSH and HTTP

Deploys a static website with Docker & NGINX

Supports Jenkins for automatic deployment

🔧 What You Need
Ansible

Docker & Docker Compose

Ubuntu server

(Optional) Jenkins for CI/CD

📁 Project Files
bash
Copy
Edit
automated-server-setup/
│
├── templates/users.yaml.j2       # User creation template  
├── web/index.html                # Website HTML  
├── web/style.css                 # Website CSS  
├── docker-compose.yaml           # Docker Compose config  
├── inventory.ini                 # Server connection details  
├── project.yaml                  # Main Ansible playbook  
├── Jenkinsfile                  # Jenkins CI/CD pipeline  
└── README.md                    # This file  
🚀 How I Used It
Set up SSH access to your server and update inventory.ini with connection info.

Run the Ansible playbook to configure the server and deploy the site:

bash
Copy
Edit
ansible-playbook -i inventory.ini project.yaml
Your static website will be available at:
http://<server-ip>:8081

(Optional) Use Jenkins and the included Jenkinsfile to automate deployments.

🧹 How to Stop the Website
On your server, run:

bash
Copy
Edit
docker compose -f /home/<user>/docker-compose.yaml down
This stops the Docker containers and cleans up the site deployment.
