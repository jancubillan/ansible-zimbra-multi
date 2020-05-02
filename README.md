ansible-zimbra-multi
====================

This role automates the process of installing multi-server Zimbra Open Source Edition v8.8.15 on CentOS 7

Requirements
------------

1. Must be a fresh CentOS 7 minimal installation
2. Static network configuration must be already set

Role Variables
--------------

Modify the variables in vars/main.yml to suit your environment

Dependencies
------------

1. Static Networking
2. Ansible Engine

Example Playbook
----------------

Copy the inventory and playbook at test/inventory and tests/site.yml. The playbook below should be similar.

    - hosts: server
      roles:
         - jancubillan.ansible_zimbra_multi

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br>
GitHub: https://github.com/jancubillan<br>
Ansible Galaxy: https://galaxy.ansible.com/jancubillan
