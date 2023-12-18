# Ansible-WP

This ansible playbook will install some docker dependencies, docker and docker compose and will create 2 docker containers one for a a mysql database and one with wordpress through a custom image created in the docker-compose.yaml file

It will also set up some nft rules which will  open only the relevant ports needed for our machine and wordpress service to run properly. The wordpress container will run automatically and it will run on port 8001.

For the authentication method used in this playbook the sshpass package must first be installed on the ansible host.

The servers/targets for ansible to run can be specified in the inventory file. To run the playbook use command  
```
ansible-playbook -i inventory playbook.yml
````

