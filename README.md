# Ansible role `mariadb install`


An Ansible role for installing and secure MariaDB in RHEL/CentOS (7,8) and Debian (9,10) and Ubunut (20.04, 19.10, 18.04, 16.04) distributions. Specifically, the responsibilities of this role are to:

## Installation
``` bash
$ ansible-galaxy install manishjuneja.mariadb
```

(1) To remove remote connection for mysql root user, set the parameter allow_remote_connections: true. E.g.:
defaults/main.yml
```yaml
allow_remote_connections: true
```

(2) **It is highly recommended to set the database root password!** Leaving the password empty is a  security risk. The role will issue a warning if the variable was not set.
defaults/main.yml
```Yaml
mysql_root_password: ''
```


## Example Playbook

```Yaml
- hosts: mariadb
  roles:
    - role: manishjuneja.mariadb
      become: yes
```

## Testing

This role is tested on Linux distributions:

- RHEL/CentOS 8
- RHEL/CentOS 7
- Debian 10
- Debian 9
- Debian 8
- Ubuntu 20.04
- Ubuntu 19.10
- Ubuntu 18.04
- Ubuntu 16.04
