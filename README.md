Role Name
=========

Configure Ansible for windows domain using kerberos authentication

Requirements
------------

Domain controller

Role Variables
--------------

This requires at least 1 Domain configuration

Domains: # List of domains that you want to allow ansible to talk to 
- Domain: homelab.local # each item in the domain list is a Domain which is the Domain name
  DomainControllers: # we then have another list of Domain Controllers
    - dc01 # These will automatically be fully qualified in the kerberos configuration

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    ---
    - name: configure ansible-for-windows
      gather_facts: true
      hosts: localhost
      become: true
    - include_role:
        name: ansible-for-windows

Extra Steps
----------------
Follow the [ansible documentation](https://docs.ansible.com/ansible/latest/user_guide/windows_winrm.html#id12) on how to use kinit to test that your kerberos configuration is working and that you are issued a ticket.