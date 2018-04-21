README.md

Ansible Tower Demo-In-A-Box
===========================

## This is a Tower demo environment in a box using Vagrant and VirtualBox.

### Notes:

1. The demo requires an internet connection on your host machine.

2. Please do not try to provision this in parallel in Vagrant. Ordering needs to happen specifically so LDAP comes up first and Tower comes up before the rest of the inventory.

3. This demo is specifically tied to a repository for the playbooks Tower will run against the remote hosts: https://github.com/dfederlein/ansible-demos To change this edit roles/tower/files/tower_project.json and roles/tower/files/tower_job_template.json

4. You will have to supply an enterprise license to configure LDAP authentication. Place your license file in roles/tower/files/tower_license.json and make sure you have added "eula_accepted": "True" as the last line in the json blob. Also be sure to define "ldaplicense: True" in the vars section of site.yml. You will also need to uncomment the LDAP VM in the first VM cluster stanza in the VagrantFile before issuing the vagrant up command.

Host Machine Requirements:

- Tested with Fedora 27 and macOS
- Ansible (version 2.4.2 or later)
- Vagrant (version 2 or later)
- VirtualBox (version 5.2 or later)
- Git
- An Internet connection to create the demo environment.
- The ability to run 6 VM's on your system.

Ansible install instructions here: http://docs.ansible.com/intro_installation.html

To install Vagrant and VirtualBox, please see http://docs.vagrantup.com/ and https://www.virtualbox.org/wiki/Downloads

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

## LDAP Authentication (OPTIONAL)

This Vagrantfile will create one OpenLDAP VM for use in experimenting with authentication, if you uncomment the LDAP VM in the first VM cluster stanza in the VagrantFile before issuing the vagrant up command.

Settings in Tower will need to be as follows to demonstrate basic functionality:

IP: `172.16.2.9`

Bind DN: `cn=tower,ou=applications,dc=example,dc=com`

Bind DN Password: `password1`

Base DN: `dc=example,dc=com`

User Search:

```
[
"ou=people,dc=example,dc=com",
"SCOPE_SUBTREE",
"(uid=%(user)s)"
]
```
Group Search:
```
[
 "ou=groups,dc=example,dc=com",
 "SCOPE_SUBTREE",
 "(objectClass=groupOfNames)"
]
```
Attribute Map:
```
{
"first_name": "givenName",
"last_name": "sn",
"email": "mail"
}
```
