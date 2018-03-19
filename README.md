Rdiff-Backup Script Ansible Role
=========

Ansible Role configures an rdiff-backup script and list of servesr to backup up from ansible inventory.

Requirements
------------

rdiff-backup is included in the Ubuntu, Debian, and Fedora repos but CentOS 6 and 7 requires EPEL.

Role Variables
--------------

rdiff_backup_server: backupserver.example.com
state: present or absent

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


### Playbook

- hosts: servers
  roles:
     - { role: /home/ben/ansible-roles/rdiff-backup-script }

### Inventory File

[servers]
servera.example.com rdiff_backup_server=backupserver.example.com state=present
serverb.example.com rdiff_backup_server=backupserver.example.com state=present
serverc.example.com rdiff_backup_server=backupserver.example.com state=present

License
-------

MIT

Author Information
------------------

Created by [Benjamin Bryan](http://b3n.org)
