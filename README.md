mysql
=====

This role installs and configures MySQL on an Ubuntu Server using mysql packages or Percona repositories.

Role Variables
--------------

- `mysql_init_system`: OS init system. (default 'upstart')
- `mysql_use_percona`: Use Percona or not (default: False)
- `mysql_version`: Server version to install (default: '5.6')
- `mysql_config_include_files`: List of files to override my.cnf (default: [])
- `mysql_databases`: List of databases (default: [])
- `mysql_users`: List of users: (default: [])
- `mysql_root_password`: Password for root user (Ex: 'SuperSecretPass')

Dependencies
------------

- dpujadas/ansible-role-python-pip

Example Playbook
----------------

    - hosts: servers
      vars:
        mysql_root_password: 'root'
        mysql_databases:
          - name: testdb
        mysql_users:
          - name: test
            password: test
      roles:
        - {
          role: mysql
        }

License
-------

MIT

[![Build Status](https://travis-ci.org/dpujadas/ansible-role-mysql.svg?branch=master)](https://travis-ci.org/dpujadas/ansible-role-mysql)