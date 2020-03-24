# Ansible Inventory

This step will have you locate and understand an ini formatted inventory file.

Examine the hosts file in the home directory

`cat hosts`{{execute}}

For the purposes of this exercise the passwords are provided here in plain-text.  In production you can use the Red Hat Ansible Platform to encrypt passwords using [credential management](https://docs.ansible.com/ansible-tower/latest/html/userguide/credentials.html).  Credential management with Ansible can also be fully integrated into CyberArk or Vault by HashiCorp.

There is an implicit group named `[all]`.  This means all hosts are part of the **all** group. To define variables in a group you can use the `:vars` which will apply these variables to all members of the group.

```
[all:vars]
ansible_user=root
ansible_ssh_pass=katacoda
```
Next we have two groups, one of the control node, just containing `host01`
```
[control_node]
host01
```

and one group named `web` with our two managed hosts

```
[web]
host02
host03
```