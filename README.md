# ansible play to manage letsencrypt wildcard certs with gandi

## How to use:
### add api key:
ansible-vault create group_vars/vault.yml

## run it:
ansible-playbook manage_letsencrypt.yml --diff -C
