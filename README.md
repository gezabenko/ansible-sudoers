Ansible - sudoers
=========

Manage sudoers settings

Requirements
------------

NA

Role Variables
--------------

```yaml
sudoers_default__host: "{{ ansible_nodename }}"
sudoers_default__npassword: false
sudoers_default__state: "present"
sudoers_default__sudoers_path: "/etc/sudoers.d/"
sudoers_default__validation: "absent"
sudoers:
  - name: allow-backup
    state: present
    user: backup
    command: /usr/local/bin/backup
```

Dependencies
------------

- [community.general.sudoers](
https://docs.ansible.com/ansible/latest/collections/community/general/sudoers_module.html#ansible-collections-community-general-sudoers-module
)

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: ansible-sudoers, tags: [ sudoers ] }

License
-------

GPLv3
