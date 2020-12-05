Ansible Role: Singularity
=========================

![CI](https://github.com/Zorlin/ansible-role-singularity/workflows/CI/badge.svg)

This role automatically configures and installs Singularity from source.

It currently only supports the latest version of Singularity, but will soon support at least the previous version.

This role currently officially supports:

* CentOS 7, CentOS 8
* Debian 9, Debian 10
* Ubuntu 18.04, Ubuntu 20.04

It should also run on Red Hat Enterprise Linux but is untested on it.

Requirements
------------

Before this role runs, you need to make sure the following dependencies are installed:

| Dependency                    | Suggested Role           |
| ----------------------------- | ------------------------ |
| Golang                        | `gantsign.golang`        |
| Git                           | `geerlingguy.git`        |

Currently you MUST use gantsign.golang to install Golang/Go Runtime.

See this role's [`molecule/default/converge.yml`](molecule/default/converge.yml) playbook for an example that works across many different OSes.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    singularity_version: '3.7.0'

In future you will be able to change singularity_version to select which version you want to install, but this doesn't do anything yet.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------


Example Playbook
----------------

```yaml
- name: Install Singularity
  hosts: all
  become: true

  roles:
    - gantsign.golang
    - zorlin.singularity
```

License
-------

MIT

Author Information
------------------

This role was created in 2020 by Benjamin Arntzen.

This role uses examples and code from [geerlingguy.awx](https://github.com/geerlingguy/ansible-role-awx) which was written by Jeff Geerling and is available under the MIT license.

This role uses examples and code from [gantsign.golang](https://github.com/gantsign/ansible-role-golang) which was written by John Freeman / GantSign Ltd and is available under the MIT license.
