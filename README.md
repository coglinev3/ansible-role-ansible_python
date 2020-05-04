# Ansible Role: ansible_python

[![Build Status](https://travis-ci.org/coglinev3/ansible-role-ansible_python.svg?branch=master)](https://travis-ci.org/coglinev3/ansible-role-ansible_python) ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/coglinev3/ansible-role-ansible_python) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://raw.githubusercontent.com/coglinev3/ansible-role-ansible_python/master/LICENSE)

Ansible needs Python 2 (version 2.6 or later) or Python 3 (version 3.5 or later) in order to work. But Python is not preinstalled on some Linux Distributions or Docker images (like on Ubuntu images). To prevent manual installation of Python on such systems, this Ansible role uses the raw module (which does not require Python) to install the Python2 or the Python3 package. Ansible can then be used normally on these systems.

You should execute this role as `pre_tasks` statement with `gather_facts` set to **false** like in the example below.

The supported Linux distributions for this role are:

* Alpine Linux 3.9,
* Alpine Linux 3.10,
* Alpine Linux 3.11,
* Debian 8 (Jessie),
* Debian 9 (Stretch),
* Debian 10 (Buster),
* Enterprise Linux 6, 
* Enterprise Linux 7, 
* Enterprise Linux 8, 
* Fedora 29,
* Fedora 30,
* Fedora 31,
* Ubuntu 16.04 LTS (Xenial Xerus),
* Ubuntu 18.04 LTS (Bionic Beaver),
* Ubuntu 19.10 (Eoan Ermine) and
* Ubuntu 20.04 (Focal Fossa).

The role was tested with Molecule and Docker on Travis-CI and with this [Multi-VM Vagrant environment](https://ansible-development.readthedocs.io/ "Vagrant environment for Developing and Testing Ansible Roles").


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

Release: 1.2.0

## License

BSD

## Author Information

This Ansible Role was created in 2020, by Cogline.v3.
