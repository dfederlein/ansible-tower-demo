README.md

Ansible Tower Demo-In-A-Box
===========================

## This is a Tower demo environment in a box using Vagrant and VirtualBox.

Host Machine Requirements:

- Tested with linux (EL/LTS) and macOS
- Ansible (version 2.3.2 or later)
- Vagrant (version 2 or later)
- VirtualBox (version 5.1 or later)
- Git 
- An Internet connection to create the demo environment.
- The ability to run 5 VM's on your system. 

Ansible install instructions here: http://docs.ansible.com/intro_installation.html

To install Vagrant and VirtualBox, please see http://docs.vagrantup.com/ and https://www.virtualbox.org/wiki/Downloads

**Note:** The demo requires an internet connection on your host machine.

## Install Instructions for macOS:

1. install homebrew ( http://brew.sh/ )
2. brew update && brew upgrade
3. ensure your path has /usr/local/bin and /usr/local/sbin before $PATH in your bash profile (~/.profile or ~/.bashrc - check after installation by issuing the command "echo $PATH")
4. brew install python
5. pip install ansible
6. install vagrant via package available here: https://www.vagrantup.com/downloads.html
7. install virtualbox from packages available here: https://www.virtualbox.org/wiki/Downloads

Now git clone this repository, cd into the directory and issue the command "vagrant up".

## Install Instructions for linux:

1. install ansible via package management or pip, per these instructions: https://docs.ansible.com/ansible/intro_installation.html
2. install vagrant per instructions and packages here: https://www.vagrantup.com/downloads.html
3. install virtualbox via OSE packages in your distro, or by packages and instructions here: https://www.virtualbox.org/wiki/Downloads
4. install the git client per your distro's package management.

Now git clone this repository, cd into the directory and issue the command "vagrant up".

## Notes:

1. This demo is specifically tied to a repository for the playbooks Tower will run against the remote hosts: https://github.com/dfederlein/ansible-demos To change this edit roles/tower/files/tower_project.json and roles/tower/files/tower_job_template.json

2. There are two Vagrantfiles included in this repo: you will need to either mv or symlink one of the. as "Vagrantfile". One (vagrant-vbox-local) is designed to work locally on a laptop or desktop in a nat'ed network environment as per standard vagrant use. The other (vagrant-vbox-ext) is specifically what I use on a spare debian box on my home network running virtualbox and vagrant, and does changes to Vagrant's networking to set the default path as bridged to my LAN network. You will probably want to use vagrant-ext-local unless you have a similar setup as mine on your LAN you want to use.