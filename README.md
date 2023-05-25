Utilizing ansible-vault to encrypt the vars file. 


A simple approach to create a vaulted variables file:
date +%s | shasum | base64 | head -c 32 > ~/.vault-password-file

cd vars
ansible-vault encrypt --vault-password-file ~/.vault-password-file aro_vars.yml --output encrypted-aro_vars.yml



to install a cluster: ansible-playbook --vault-password-file ~/.vault-password-file cluster-build.yml

to delete a cluster: ansible-playbook --vault-password-file ~/.vault-password-file delete_cluster.yml


