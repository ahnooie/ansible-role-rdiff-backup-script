Rdiff-Backup Script Ansible Role
=========

Ansible Role automates backups by configuring an rdiff-backup script and list of servers to backup up from ansible inventory.  It will install rdiff-backup on both the clients and server.  On the server it creates a script and cron job to pull backups from clients periodically using rdiff-backup and ssh.  It will also generate ssh keys on the server and add those to the client's authorized_keys file for passwordless ssh authentication.  As servers are added and removed (marked present or absent) in ansible the backup list is automatically updated.

Requirements
------------

This role should work on any popular Linux distribution for the client and backup server as long as rdiff-backup.

rdiff-backup must be available in the repos.  It is included in later versions of Ubuntu, Debian, and Fedora.  For RedHat or CentOS 6 and 7 you'll need EPEL repos enabled.

Role Variables
--------------

Required:

```
rdiff_backup_server: backupserver.example.com
```

Optional:
```
state: present (default) or absent
rdiff_backup_command: (optional, overrides default command)
rdiff_prune_command: (optional, overrides default command)
rdiff_cron_minute: (defaults to 43)
rdiff_cron_hour: (defaults to 1)
```

Dependencies
------------

none

Example Playbook
----------------

### Playbook

```
- hosts: servers
  roles:
    - { role: ahnooie.rdiff-backup-script, rdiff_backup_server: backupserver.example.com }
```

### Inventory File

```
[servers]
servera.example.com
serverb.example.com
serverc.example.com
```

License
-------

MIT

Author Information
------------------

Created by [Benjamin Bryan](https://b3n.org)
