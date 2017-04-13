# obiba-ansible-deployment-aegir
Ansible script to deploy drupal site using Aegir
## Requires
- Ansible : [ansible doc](http://docs.ansible.com/ansible/index.html)
- Aegir on the distant server : [Aegir Doc](http://docs.aegirproject.org/en/3.x/community/)
## Installation 
```bash
# sudo apt-add-reposito- Aegir on the distant serverry -y ppa:ansible/ansible
# sudo apt-get update
# sudo apt-get install -y ansible
```
## Usage
- add a host to /etc/ansible/hosts
```bash
[local]
127.0.0.1
```
- clone the repo in an ansible folder 
```bash
# mkdir ansible_deploy
# cd ansible_deploy
# git clone https://github.com/obiba/obiba-ansible-deployment-aegir.git
```
- create an Playbook file deploy.yaml in the 'ansible_deploy' folder
```bash
---
- hosts: local
  roles:
    - ansible-deployment-aegir
```
- run the playbook script : 
```bash
# ansible-playbook -u aegir deploy.yml
```

