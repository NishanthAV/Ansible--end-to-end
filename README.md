# Ansible--end-to-end
Ansible
Code
Login to aws console
create 2 ec2 instance host and target server
login via ssh
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install ansible
ansible --version
ssh-keygen #on both ec2 instances
##copy id_rsa.pub key of host server and paste it in authorized keys in target
#check by typing
ssh <private_ip>
#create file in target server using adhoc commands
sudo vim inventory
<private_ip>
ansible -i inventory all -m  "shell" -a "touch devopsclass"
ls -ltr & du -sh
ansible -i inventory all -m "copy" -a "src: /srv/myfiles/foo.conf" "dest:/etc/foo.conf" "owner:foo" "group:foo" "mode: '0644'"
sudo nano first-playbook.yaml
```
---
- name: Install and Start nginx
  hosts: all
  tasks:
    - name: Install nginx package
      package:
        name: nginx
        state: present

    - name: Start nginx service
      service:
        name: nginx
        state: started

```
ansible-playbook -i inventory first-playbook.yml
mkdir second-Playbook
cd playbook/
ansible-galaxy role init kubernetes
ls -ltr kubernetes

```
