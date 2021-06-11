# An automated build for git NGINX Docker Containers
This project contains a script, "create-all", that generates additional scripts, a Dockerfile, and configurations to automatically build and run a Docker container with git and NGINX along with pre-staging a repo.

## Getting Started
Begin with a fresh Ubuntu Server x64 16+ Machine: e.g. https://mirror.math.princeton.edu/pub/ubuntu-iso/16.04.7/ubuntu-16.04.7-server-amd64.iso *Include the openSSH package for remote access. If not pre-configured during install, configure network interface for public network and DNS access from the new machine.

Once it's confirmed that you have good connectivity, run the "create-all" script.

After the script completes, it finishes with a "clone" command and synchronizes with the container's generated master.
Next, create some files in the "admin" folder, or use the "gen" command to create some example files to push.
Then, use the "push" command to send a commit with those latest files.
An https website will be available at the host system's IP that lists the latest files.

### Prerequisites
Install Ubuntu Server x64, tested exclusively on 16.04

### Installing
Create a copy (clone / fetch) of this project, or alternatively copy the "create-all" script to the directory where the system will initialize. A home directory is fine. Run `chmod +x create-all` and then run the script with `.\create-all`
![Initial Clone and Run](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen001.png)

### Running
This project will stage the following commands:  
`install` - Install the Docker image with the latest Dockerfile  
`start` - Start the Docker container  
`stop` - Stop the Docker container  
`clean` - Prune Docker containers  
`render` - Show the current Docker container web page using Lynx  
`vanish` - Remove all project files, including this script  
`clone` - Clone the Admin Repo from the Docker container to the local system into the admin folder  
`push` - Push any changes in the local admin folder to the repo  
`gen` - Generate random scripts in the admin folder for testing  
![Cloning from the Docker Container and root directory](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen002.png)
  
### Examples
After cloning from the Docker Container repo, there is a single file, test.sh, in the admin folder. This script simply runs a `pwd` command.
![Admin directory after initial cloning](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen003.png)  
![The web page after initial cloning](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen004.png)  
However, using the `./gen` command will add a new script that outputs the Unix Time as of the script generation.    
![Several generated scripts](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen005.png)  
Then, the `./push` command can be used to commit these new scripts to the Docker repo  
![Push command adds these new scripts](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen006.png)  
And now the web page shows these new script outputs  
![Generated scripts show on the container website](https://raw.githubusercontent.com/jawcode/gitNginxDockerBuild/master/screen007.png)  

## Authors
J.A. Waters

## License

This project is licensed under the MIT License
