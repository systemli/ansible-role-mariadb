# Ansible role to install and configure MariaDB on Debian systems

[![Build Status](https://github.com/systemli/ansible-role-mariadb/workflows/Integration/badge.svg?branch=main)](https://github.com/systemli/ansible-role-mariadb/actions?query=workflow%3AIntegration)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-mariadb-blue.svg)](https://galaxy.ansible.com/systemli/mariadb/)

The role installs and configures the MariaDB server on a Debian system.

* Installs `automysqlbackup` per default
* Sets `innodb_buffer_pool_instances` to number of vCPUs
* Sets `innodb_buffer_pool_size` to (total memory / 2)

The role is tested on Debian 9-11.

## Variables and their defaults

See `defaults/main.yml`.

## Installation

Using ansible galaxy cli:

```bash
ansible-galaxy install systemli.mariadb
```

Using ansible galaxy requirements file:

```yaml
- src: systemli.mariadb
```

## Testing & Development

For developing and testing the role we use Github Actions, Molecule, and Vagrant. On the local environment you can easily test the role with

```
molecule test
```

Requires Molecule, Vagrant and `python-vagrant` to be installed. 

# License

This Ansible role is licensed under the GNU GPLv3 or later.

# Author

[https://www.systemli.org](https://www.systemli.org)
