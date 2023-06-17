# Jupyter Lab Skeleton
<figure style="text-align: left; font-style: italic; font-size: smaller; text-indent: 2em; border: none; margin: 0.5em; padding: 0.5em;">
<img src="https://urbansec.github.io/assets/img/repo_images/lab_skeleton.jpg" alt="Skeleton doing science in lab" style="display: block; margin-left: auto; margin-right: auto; width: 50%"/>
<figcaption>Lab Skeleton</figcaption>
</figure>

## Intro
This is a base skeleton for building a quick JupyterLab server using docker.
It relies on the Jupyter Stacks docker images.
Because it's so simple, it should be pretty easy to modify to suit different systems.
It should also work with most of the Jupyter Stacks images.
It is intended for use on a Linux host.

## Files
- Dockerfile: Placeholder Dockerfile included in case modifications are desired
- docker_compose.yml: Defines some environment variables and mounts
- .env: Defines additional environment variables
- jupyter_server_config.json: Empty config file for mount, password will be stored here.

## Prerequisites
- Install docker and docker-compose
- Directory structure as outlined below, or you can edit the paths to fit your directory structure
- NOTE: the requirement is that a project folder exists that contains the "jupyter_server_config.json" file and a "work" subfolder.

## Use
1. `git clone https://github.com/urbansec/LabStarter.git` or download files
1. Configure file system
   1. `mkdir $HOME/working`
   1. `mkdir $HOME/working/Jupyter_Projects`
   1. `mkdir $HOME/working/Jupyter_Projects/project_name`
   1. `mkdir $HOME/working/Jupyter_Projects/project_name/work`
1. Edit .env file
   1. Set "INS_HOME" to path of your home directory (`echo $HOME` in most shells)
   1. Set "INS_PROJECT" to whatever project_name you chose
1. Copy "jupyter_server_config.json" to "$HOME/working/Jupyter_Projects/project_name/work/"
1. Edit Dockerfile to further customize image if desired.
1. Launching and accessing the container
   1. `sudo docker-compose up`
   1. Use ip, port, token to access Jupyter and set a password
   1. After the password is set, you can use `sudo docker-compose up -d`

## Resources
- Getting started with Docker https://docs.docker.com/get-started/
- Jupyter Stacks https://jupyter-docker-stacks.readthedocs.io/en/latest/
