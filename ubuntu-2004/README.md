# Install prosody container with ansible role

## Requirements

- ansible 2.9 installed

## Steps to provision server

- update inventory.yaml and put there the host with correct hostname. This hostname and IP
- make sure you have access to the host with your key like
- you can specify user distinct from root in variable ansible_user in inventory.yaml (see example) 
- prodibe the keys in files/pub_keys/*.pub they will be attached to the setup_user
- all the defaults variables see in the defaults/main.yaml
- you can specify any of them in the inventory (see example)
- check that you are able to communicate with the server using command
```sh
ansible -m ping hostname
``` 
- install all the stuff with the command
```
ansible-playbook prosody.yaml -i inventory.yaml
```
- also you can use the tags
```
ansible-playbook prosody.yaml -i inventory.yaml --tags='install'
```
```
ansible-playbook prosody.yaml -i inventory.yaml --tags='install, configure'
```
```
ansible-playbook prosody.yaml -i inventory.yaml --tags='configure'
```