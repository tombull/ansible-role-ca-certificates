ca_certificates
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-ca_certificates.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-ca_certificates)

The purpose of this role is to install and configure ca_certificates on your system.

[Unit tests](https://travis-ci.org/robertdebock/ansible-role-ca_certificates) are done on every commit and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-ca_certificates/issues)

To test this role locally please use [Molecule](https://github.com/metacloud/molecule):
```
# Docker test:
pip install molecule ara
molecule test
# Vagrant tests
molecule test --scenario-name vagrant
```
There are many scenarios available, please have a look in the `molecule/` directory.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/ca_certificates.png "Dependency")

Requirements
------------

- A system installed with required packages to run Ansible. Hint: [bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap).
- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the last 3 release of Ansible.)

Role Variables
--------------

- ca_certificates_parameter: Description of values. [default: value]

Dependencies
------------

- None known.

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|ansible 2.7|ansible devel|
|------------|-----------|-----------|-----------|-----------|-------------|
|alpine-edge*|yes|yes|yes|yes|yes*|
|alpine-latest|yes|yes|yes|yes|yes*|
|archlinux|yes|yes|yes|yes|yes*|
|centos-7|yes|yes|yes|yes|yes*|
|centos-latest|yes|yes|yes|yes|yes*|
|debian-latest|yes|yes|yes|yes|yes*|
|debian-stable|yes|yes|yes|yes|yes*|
|debian-unstable*|yes|yes|yes|yes|yes*|
|fedora-latest|yes|yes|yes|yes|yes*|
|fedora-rawhide*|yes|yes|yes|yes|yes*|
|opensuse-leap|yes|yes|yes|yes|yes*|
|ubuntu-artful|yes|yes|yes|yes|yes*|
|ubuntu-devel*|yes|yes|yes|yes|yes*|
|ubuntu-latest|yes|yes|yes|yes|yes*|

A single star means the build may fail, it's marked as an experimental build.

Example Playbook
----------------

```
---
- name: ca_certificates
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.ca_certificates
      ca_certificates_parameter: value
```

To install this role:
- Install this role individually using `ansible-galaxy install robertdebock.ca_certificates`

Sample roles/requirements.yml: (install with `ansible-galaxy install -r roles/requirements.yml
```
---
- name: robertdebock.bootstrap
- name: robertdebock.ca_certificates
```

License
-------

Apache License, Version 2.0

Author Information
------------------

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>