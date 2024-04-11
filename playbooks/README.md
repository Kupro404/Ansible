# Ansible-WP
This repo includes an ansible playbook to create two containers one for wordpress and one for its database through a custom image created in the docker-compose.yaml file. Within the ansible directory there is also a docker role to install docker and docker compose if needed and it includes some basic nft rules which will  open only the relevant ports needed for your host machine and wordpress service to run properly. There is also a docker-rootless role for the rootless installation it requires though for you to change the user in the rootless_install.yml file to your user. The wordpress container will run automatically and it will run on port 8001. You can skip starting the containers with  
```
--skip-tags start_wp
```
and you can also avoid copying and loading the nft rules with the bellow tags
```
--skip-tags nft
--skip-tags load_nft
```
Have in mind that skipping to start the containers will also result in not building them so you will have to do that manually when needed. Furthermore as the module to start the containers is a community one you will have to first install it with 
```
ansible-galaxy collection install community.docker
```

For the authentication method used in this playbook the sshpass package must first be installed on the ansible host.
```
apt install sshpass -y 
```
The servers/targets for ansible to run can be specified in the inventory file. To run the playbook use command  
```
ansible-playbook playbook.yml
````
and remember to run from within the ansible directory.

This playbook can work for Debian and Redhat systems. 
