# MikroTik RouterOS Backups

Peforms backups of MikroTik RouterOS Devices and will diff and create HTML files, which will be emailed to specified email addresses.

Saves the configs in backup location defined in ```configs_dir``` in the vars/main.yml file. (default is /ansible_backups/mikrotik/)

By default, Ansible uses a small terminal screen size.  This causes commands to be broken down into multiple lines in the export.  If this is an undesired affect, you can increase the terminal size by adding a bit of text to the username.
Example:
```
ansible_user=admin+cet512w
```
In this example, the router username is ansible and it changes the width of the terminal to 512.  This allows for a much longer output line if desired.

# Current Known Issues

* Some diff reports fail, I suspect due to timing out on slower host servers.
