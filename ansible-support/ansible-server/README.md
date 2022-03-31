# ansible-support
Place file `50-no-guest.conf` and `sssd.conf` in your home directory

To running the playbook, execute this command:
ansible-playbook -i hosts --ask-vault-pass --extra-vars='@passwd.yml' production.yml

The `pc_support` and `new` group has the same password while `pass_beda` have different password
currenty our vault just saving the credential of pc_support group



