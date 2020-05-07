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

Create an inventory file similar below:

    # vi inventory

    [zimbra_all:children]
    zimbra_ldap
    zimbra_mta
    zimbra_proxy
    zimbra_mailbox

    [zimbra_ldap]
    ldap.example.com ansible_host=192.168.122.111

    [zimbra_mta]
    mta.example.com ansible_host=192.168.122.112

    [zimbra_proxy]
    proxy.example.com ansible_host=192.168.122.113

    [zimbra_mailbox]
    mailbox.example.com ansible_host=192.168.122.114

Create playbook similar below:

    # vi site.yml

    ---
    - hosts: zimbra_all
      roles:
        - jancubillan.ansible_zimbra_multi

Then run as follows:

    # ansible-playbook -i inventory site.yml

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br>
GitHub: https://github.com/jancubillan<br>
Ansible Galaxy: https://galaxy.ansible.com/jancubillan
