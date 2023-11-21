# Ansible-Pull

This ansible playbook will install some docker dependencies, docker and docker compose and will create 2 docker containers one for a a mysql database and one with wordpress. It will also set up some nft rules which will  open only the relevant ports needed for our machine and wordpress service to run properly. The wordpress container will run automatically and it will run on port 8001.
