To prep clean pie OS, override all settings in the ansible.cfg

Note:

The --user is the admin account created during inital setup of the pie


1) Prep the raspberry pi system disk using raspberry pi imager
2) Clone this repo to a local server, where you want to provision from
3) Edit and add the ip address of the server you want to provision to the bootstrap.ini file
4) Run the bootstrap playbook (in check mode)  - ansible-playbook --user admin --ask-pass --become-user root --ask-become-pass --ask-vault-pass bootstrap.yml -i "<ipaddress>," --check
5) Run the bootstrap playbook in real mode ansible-playbook --user admin --ask-pass --become-user root --ask-become-pass --ask-vault-pass bootstrap.yml -i "<ipaddress>,"
6) Install everything else, after initial prep - ansible-playbook site.yml
