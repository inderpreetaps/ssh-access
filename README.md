# ssh-access
Grant/Revoke SSH access to a group of instances to a user

### Use below given command to add new user and grant SSH access
ansible-playbook -i inventory/ -e "action=grant" playbooks/ssh.yml

### Use below given command to grant SSH access to an existing user
ansible-playbook -i inventory/ -e "action=grant" playbooks/ssh.yml --skip-tags=add

### Use below given command to revoke SSH access from a user
ansible-playbook -i inventory/ -e "action=revoke" playbooks/ssh.yml --skip-tags=remove

### Use below given command to remove user, hence revoke SSH access as well
ansible-playbook -i inventory/ -e "action=revoke" playbooks/ssh.yml


## Notes
 - Under [instances] group in inventory/hosts files please make sure to add IPs or DNS of target instances.
 - Update the varibale "user_name" and "user_des" as per requirements. You can add multiple values as well to run the action for mutiple users at a time.
 - Make sure to create a directory under "sshkeys" directory of same name as user name and put its SSH pub key under it.
