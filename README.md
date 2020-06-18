# MikroTik RouterOS Backups

Peforms backups of MikroTik RouterOS Devices and will diff and create HTML files, which will be emailed to specified email addresses.

Saves the configs in backup location defined in ```configs_dir``` in the vars/main.yml file. (default is /ansible_backups/mikrotik/)

Modify SED commands as approprate in your environment to cleanup dynamic lines in your configuration files, that you don't want included in the diffs.
Make sure not to modify any of the SED commands that are there now, as they cleanup the config file from the raw export.

Current Issues:
* SED command to remove the \\ and multiple spaces only removes the \\, it doesn't remove the spaces.
* May not properly handle custom scripts in the config.