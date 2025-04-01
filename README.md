# OpenCTI
This project will cover the deployment of the OpenCTI, creating connecors to injest data feeds (i.e, MISP, Alien, and darkweb feeds).
My goal for this platform is to act as my personal modularized CTI platform that will enable me to focus on Russian based threat actors. 
![image](https://github.com/user-attachments/assets/4e05bef0-8858-4f90-b592-d27a8cff2f5e)

#**OpenCTI Build**
**System Requirements**
1. Ubuntu 20.04.6  Live Server (This is what I used)
2. Memory 16gb
3. Core 16
4. Hard Disk 100gb

**Steps to Build the OpenCTI instance**
*There are several walkthroughs that I had issues with, this what worked for me and my level of understanding. I will provide the commands and what they do. 
I will keep them to 1 sentence here. 
*Make sure you have docker running and check the status

1. sudo apt-get install apt-transport-https (allows us to pull from both HTTP and HTTPS)
2. sudo apt-get install ca-certificates (install and manage CA certs on our system)
3. sudo apt-get install curl (optional if you don't have curl binary on your system)
4. sudo apt-get install gnupg-agent (this is background process that will allow us to manage our GPG keys.
5. sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - (we are importing the docker gpg keys)
6. sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" (This is pulling the official stable repo for the AMD 64 bit architecture.)
7. sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose (We download docker and the command line tools, container runtime, and docker compose)
8. sudo docker swarm init --advertise-addr <ip address> (we are going to initlize docker swarm and make our ip address available within our network)
9. sudo mkdir -p /opt/portainer && cd /opt/portainer (we are making the portainer directory and moving into the directory)
10. sudo curl -L https://downloads.portainer.io/portainer-agent-stack.yml -o portainer-agent-stack.yml (Here we are getting the portainer agent file and putting it in a yaml file)\
11. sudo nano ./portainer-agent-stack.yml (here we are going to open our portainer agent file and make some edits, it will be posted in this repo.)
12. sudo docker stack deploy --compose-file=portainer-agent-stack.yml portainer (we are deploying out instance of portainer)
13 Login to your portainer instance and add the OpenCTI docker compose and env files. (they will be posted here as well)


//Next steps
//Fix misp connector
//fix investigate alien connector
