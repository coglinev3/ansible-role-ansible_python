# Ansible Role: ansible_python

[![Build](https://github.com/coglinev3/ansible-role-ansible_python/actions/workflows/build.yml/badge.svg)](https://github.com/coglinev3/ansible-role-ansible_python/actions/workflows/build.yml) ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/coglinev3/ansible-role-ansible_python) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://raw.githubusercontent.com/coglinev3/ansible-role-ansible_python/master/LICENSE)

New Ansible versions need Python 3 (version 3.9 or later) in order to work.
But Python is not preinstalled on some Linux Distributions or Docker images.
To prevent manual installation of Python on such systems, this Ansible role
uses the raw module (which does not require Python) to install the Python
package. Ansible can then be used normally on these systems.


You should execute this role as `pre_tasks` statement with `gather_facts` set to **false** like in the example below.

The supported Linux distributions for this role are:

* Alpine Linux 3.14,
* Alpine Linux 3.15,
* Alpine Linux 3.16,
* Alpine Linux 3.17,
* Alpine Linux 3.18,
* Alpine Linux 3.19,
* Alpine Linux 3.20,
* Alpine Linux 3.21,
* Alpine Linux 3.22,
* Amazon Linux 2023,
* Debian 11 (Bullseye),
* Debian 12 (Bookworm),
* Debian 13 (Trixie),
* Enterprise Linux 9, 
* Enterprise Linux 10, 
* Fedora 40,
* Fedora 41,
* Fedora 42,
* Ubuntu 22.04 LTS (Jammy Jellyfish),
* Ubuntu 24.04 LTS (Noble Numbat).

The role was tested with Molecule and Docker on GitHub and with this [Multi-VM Vagrant environment](https://ansible-development.readthedocs.io/ "Vagrant environment for Developing and Testing Ansible Roles").


## Requirements

None.

## Role Variables

None.

## Dependencies

None.

## Example


```yml
---

- hosts: all
  become: true
  # switch gather facts off, becauѕe gather facts needs python
  gather_facts: false
  pre_tasks:
    - name: "Install python if needed"
      include_role:
        name: "coglinev3.ansible_python"
    - name: Gather facts
      setup: # switch gather facts on
  tasks:
    - name: Your other tasks comes here
```

## Version

Release: 1.14.5

## License

BSD

## Author Information

Copyright &copy; 2020 - 2024 Cogline.v3.
