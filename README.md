# MikroTik RouterOS Backups

Peforms backups of MikroTik RouterOS Devices and will diff and create HTML files, which will be emailed to specified email addresses.

Saves the configs in backup location defined in ```configs_dir``` in the vars/main.yml file. (default is /ansible_backups/mikrotik/)

### Multiline configs
By default, Ansible uses a small terminal screen size.  This causes commands to be broken down into multiple lines in the export.  If this is an undesired affect, you can increase the terminal size by adding a bit of text to the username.
Example:
```
ansible_user=ansible+cet512w
```
In this example, the router username is ansible and it changes the width of the terminal to `512`.  This allows for a much longer output line if desired.  This won't have an effect on User Scripts, as routeros will break them down into multiple lines regardless of this setting if they contain new lines within the script itself.

### Options
You can enable the install prerequisite job once to get them installed on your ansible server, by setting `install_prerequisites: true`. Then leave disabled after the first run. This doesn't need to happen on a regular basis.

### Hosts File
You will need to create a hosts file.  Most people use 'hosts'.  Here is an example of what it may contain
```
[mikrotik]
192.168.1.1 ansible_user=admin+cet512w ansible_password=mypassword
```

If your username or password is the same across all devices, you might instead modify the `group_vars/mikrotik.yml` file and omit the `ansible_user` and `ansible_password` variables from the hosts file.


# Current Known Issues

* Some diff reports fail, I suspect due to timing out on slower host servers.
