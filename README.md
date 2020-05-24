# Ansible role to install and configure MariaDB on Debian systems

[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-mariadb-blue.svg)](https://galaxy.ansible.com/systemli/mariadb/) [![Build Status](https://travis-ci.org/systemli/ansible-role-mariadb.svg?branch=master)](https://travis-ci.org/systemli/ansible-role-mariadb)

The role installs and configures the MariaDB server on a Debian system.

* Installs `automysqlbackup` per default
* Sets `innodb_buffer_pool_instances` to number of vCPUs
* Sets `innodb_buffer_pool_size` to (total memory / 2)

The role is tested on Debian Jessie, Stretch, and Buster.

## Variables and their defaults

See `defaults/main.yml`.

# License

This Ansible role is licensed under the GNU GPLv3 or later.

# Author

[https://www.systemli.org](https://www.systemli.org)
