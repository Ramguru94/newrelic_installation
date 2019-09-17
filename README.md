# NewRelic Installation Using Ansible
In this project we are going to install NewRelic Agent in all our target machine server using Ansible
### OS Used
- Ubuntu 18.04
### Tools Used

 - Ansible

### Things to do before we start
- Install Ansible - [Link](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-apt-ubuntu)
- Configure SSH in all our Target remote machines so that Ansible can connect to the remote machine through SSH protocol. 

### How to run the Playbook

 - Navigate to the Agent folder
			 `cd ansible/agent`
			 
 - Open **newrelic_agent_install.yml** using your favourite editor.
 `vi newrelic_agent_install.yml`
 
 - Enter the target host machine name under 
 `hosts: <remote_machine>`

- Under `vars:` enter the ubuntu version's code name and license key that you would have obtained after registering with Newrelic plans

```
os_codename: xenial
license_key:  xxxxxxxxxxxxxxxxxxxx
```

- Now you can run the playbook by the following command
`ansible-playbook newrelic_agent_install.yml -e server_name=<target_machine>`

Here the **server_name** would be the name of the remote machine  of the remote machine that you would like to give it to the remote server so that ir can be viewed in the Newrelic web Console. This **server_name** can be any unique name or your hostname of your remote server


```
