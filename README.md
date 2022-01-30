# vagrant-ansible

ansible-playbook --ask-pass -i hosts playbook.yml -vvv

ansible-playbook --private-key=~/.vagrant.d/insecure_private_key -u vagrant -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory -i hosts playbook.yml