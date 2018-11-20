# An automated build for git NGINX Docker Containers
This project contains a script, "create-all", that generates additional scripts, a Dockerfile, and configurations to automatically build and run a Docker container with git and NGINX along with pre-staging a repo.

## Getting Started
Begin with a fresh Ubuntu Server x64 16+ Machine: http://mirror.math.princeton.edu/pub/ubuntu-iso/16.04.5/ubuntu-16.04.5-server-amd64.iso *Include the openSSH package for remote access. If not pre-configured during install, configure network interface for public network and DNS access from the new machine. Once it's confirmed that you have good connectivity, run the "create-all" script.

### Prerequisites
Install Ubuntu Server x64, tested exclusively on 16.04

### Installing
Create a copy (clone / fetch) of this project, or alternatively copy the "create-all" script to the directory where the system will initialize. A home directory is fine. Run `chmod +x create-all` and then run the script with `.\create-all`
![Initial Clone and Run](https://raw.githubusercontent.com/jacode/gitNginxDockerBuild/master/screen001.png)

### Running
This project will stage the following commands:  
install - Install the Docker image with the latest Dockerfile  
start - Start the Docker container  
stop - Stop the Docker container  
clean - Prune Docker containers  
render - Show the current Docker container web page using Lynx  
vanish - Remove all project files, including this script  
clone - Clone the Admin Repo from the Docker container to the local system into the admin folder  
push - Push any changes in the local admin folder to the repo  
gen - Generate random scripts in the admin folder for testing  
![Cloning from the Docker Container and root directory](https://raw.githubusercontent.com/jacode/gitNginxDockerBuild/master/screen002.png)

## Authors
J.A. Waters

## License

This project is licensed under the MIT License

## Acknowledgments

* The Empire Did Nothing Wrong
