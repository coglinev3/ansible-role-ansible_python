# Ansible Role: ansible_python

[![Build](https://github.com/coglinev3/ansible-role-ansible_python/actions/workflows/build.yml/badge.svg)](https://github.com/coglinev3/ansible-role-ansible_python/actions/workflows/build.yml) ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/coglinev3/ansible-role-ansible_python) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://raw.githubusercontent.com/coglinev3/ansible-role-ansible_python/master/LICENSE)

Ansible needs Python 2 (version 2.6 or later) or Python 3 (version 3.5 or later) in order to work. But Python is not preinstalled on some Linux Distributions or Docker images (like on Ubuntu images). To prevent manual installation of Python on such systems, this Ansible role uses the raw module (which does not require Python) to install the Python2 or the Python3 package. Ansible can then be used normally on these systems.

>**Warning:** 
Ansible 2.11 will make Python 3.8 a soft dependency for the control node, but will function with the aforementioned requirements. Ansible 2.12 will require Python 3.8 or newer to function on the control node. Starting with Ansible 2.11, the project will only be packaged for Python 3.8 and newer.


You should execute this role as `pre_tasks` statement with `gather_facts` set to **false** like in the example below.

The supported Linux distributions for this role are:

* Alpine Linux 3.12,
* Alpine Linux 3.13,
* Alpine Linux 3.14,
* Alpine Linux 3.15,
* Alpine Linux 3.16,
* Alpine Linux 3.17,
* Alpine Linux 3.18,
* Amazon Linux 2023,
* Debian 10 (Buster),
* Debian 11 (Bullseye),
* Debian 12 (Bookworm),
* Enterprise Linux 7, 
* Enterprise Linux 8, 
* Enterprise Linux 9, 
* Fedora 34,
* Fedora 35,
* Fedora 36,
* Fedora 37,
* Fedora 38,
* Ubuntu 16.04 LTS (Xenial Xerus),
* Ubuntu 18.04 LTS (Bionic Beaver),
* Ubuntu 20.04 LTS (Focal Fossa) and
* Ubuntu 22.04 LTS (Jammy Jellyfish).

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

Release: 1.12.0

## License

BSD

## Author Information

Copyright &copy; 2023 Cogline.v3.
