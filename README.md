# Install Keepalived x Nginx with Ansible on Ubuntu 20
### Adjust with your env
- #### <i> playbook.yaml </i>
```
vars:
    vip: 192.168.200.36
    master_ip: "{{ hostvars['master']['ansible_host'] }}"
    backup_ip: "{{ hostvars['backup']['ansible_host'] }}"
    interface: "{{ ansible_default_ipv4.interface }}"
```
- #### <i> hosts </i>
```
[nodes]
master ansible_host=192.168.200.37
backup ansible_host=192.168.200.38

[all:vars]
ansible_connection=ssh
ansible_user=user
ansible_ssh_pass=passwd
ansible_become_password=passwd
```
### Run playbook
``` bash
ansible-playbook -i hosts playbook.yaml
``` 
 
### Open your favorite browser and access
http://192.168.200.36
