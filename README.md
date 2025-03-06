# Corr Suite Integration Installer

This page has instructions and files needed to instal the integration piece for Corr Suite.

### 1. Technology used

We are using docker compose for installing the integration components. It is recomended to use Ubuntu 22.04 or above machine for this installtion. However for testing, windows with WSL 2 can be used.

### 2. Installing Docker on Ubuntu Machine

You can download the script to install docker on ubuntu and run it.

`curl -o install_docker.sh https://raw.githubusercontent.com/eps-dockermanager/corr-intg-installer/refs/heads/main/install_docker.sh`

Change the permission to allow execution

`sudo chmod +x install_docker.sh`

`sudo ./install_docker.sh`

Press `y` for the questions asked. This should install the docker on Ubuntu machine.

### 3. Running WSL-2 on windows machine

If you want to test on windows machine, please enable Ubuntu 22.04 using WSL.

Start a command prompt as **administrator** and run the following command.

`wsl --install Ubuntu-22.04`

Wait for the installation to complete. When prompted enter the username and password for the Ubuntu machine.

After installation, you should see the Ubuntu Console. Proceed to install Docker using the step #2

### 4. Login to github docker repository

Run the following command to login to github docker repo.

`sudo docker login ghcr.io`

Username: eps-dockermanager

Password: Please contact dev team for the password.

Note: Github docker repo gives a false positive response. So be careful while entering the password if you are doing a copy paste.

### 5. Steps to Install the integration app

You can download the installation script from the github and install the integration app. Follow the steps given below.

`curl -o install.sh https://raw.githubusercontent.com/eps-dockermanager/corr-intg-installer/refs/heads/main/install.sh`

`sudo chmod +x install.sh`

`sudo ./install.sh`

When prompted, enter the version you want to install. It will be of the format v(x.x.x)
