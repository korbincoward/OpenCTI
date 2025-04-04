# OpenCTI
This project will cover the deployment of the OpenCTI, creating connecors to injest data feeds (i.e, MISP, Alien, and darkweb feeds).
My goal for this platform is to act as my personal modularized CTI platform that will enable me to focus on Russian based threat actors. 
![image](https://github.com/user-attachments/assets/4e05bef0-8858-4f90-b592-d27a8cff2f5e)

#**OpenCTI Build**
**System Requirements**
1. Ubuntu 20.04.6  Live Server (This is what I used)
2. Memory 16gb
3. Core 16
4. Hard Disk 200gb

**Steps to Build the OpenCTI instance**
*There are several walkthroughs that I had issues with, this what worked for me and my level of understanding. I will provide the commands and what they do. 
I will keep them to 1 sentence here. 
*Make sure you have docker running and check the status

- sudo apt install docker-compose
- sudo mkdir /opt/opencti
- sudo git clone https://github.com/OpenCTI-Platform/docker.git
- cd docker/
- sudo cp .env.sample .env
- sudo systemctl status docker
- sudo  docker-compose up -d
If docker-compose fails to start you will need to run the following:
- sudo apt-get remove docker-compose
- sudo curl -SL https://github.com/docker/compose/releases/latest/download/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
  You should now be able to run the docker-compose up command.
