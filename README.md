Ansible - sudoers
=========

Manage sudoers settings

Requirements
------------

NA

Role Variables
--------------

Implemented all ansible module parameters, but only `name` variable is necessary.

```yaml
sudoers_default__host: "{{ ansible_nodename }}"
sudoers_default__nopassword: false
sudoers_default__state: "present"
sudoers_default__sudoers_path: "/etc/sudoers.d/"
sudoers_default__validation: "absent"
sudoers__group:
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

```yaml
    - hosts: servers
      roles:
         - { role: ansible-sudoers, tags: [ sudoers ] }
```

License
-------

GPLv3
