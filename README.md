MikroTik RouterOS Backups
=========

This role will backup routeros devices and write the config to a file in /ansible_backups/mikrotik/{{ date }}. Will also cleanup configs with sed if you enter the regex lines in the vars/main.yml

Requirements
------------

NA

Role Variables
--------------

Timeout is currently set to 2 minutes in the variable file.

Dependencies
------------

NA

Example Playbook
----------------

---
- name: Backup routeros devices
  hosts: mtk1
  gather_facts: no
  strategy: free
  vars:
# I recommend setting the timeout to two minutes or even longer depending on how long it takes the device to pull the file.
    ansible_command_timeout: 120

  roles:
    - mtk-ros-backup

License
-------

BSD

Author Information
------------------

Zachary Biles 2020
