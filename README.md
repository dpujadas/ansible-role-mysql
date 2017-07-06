mysql
=====

This role installs and configures [Percona MySQL](https://www.percona.com/software/mysql-database/percona-server) on an Ubuntu Server.

Role Variables
--------------

- `mysql_init_system`: OS init system. (default 'upstart')
- `mysql_version`: Server version to install (default: '5.7')
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
        mysql_datadir: '/srv/mysql'
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