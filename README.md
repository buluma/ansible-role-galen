# Ansible role [galen](https://galaxy.ansible.com/ui/standalone/roles/buluma/galen/documentation)

Automated testing of look and feel for your responsive websites.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-galen/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-galen/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-galen.svg)](https://github.com/buluma/ansible-role-galen/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-galen.svg)](https://github.com/buluma/ansible-role-galen/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-galen.svg)](https://github.com/buluma/ansible-role-galen/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/galen)](https://galaxy.ansible.com/ui/standalone/roles/buluma/galen/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-galen/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  tasks:
    - name: "Include buluma.galen"
      ansible.builtin.include_role:
        name: "buluma.galen"
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-galen/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - name: buluma.bootstrap
    - name: buluma.git
    - name: buluma.java
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-galen/blob/master/defaults/main.yml):

```yaml
---
# defaults file for galen

galen_packages:
  - unzip

galen_version: 2.4.4
galen_url: "https://github.com/galenframework/galen/releases/download/galen-{{ galen_version }}/galen-bin-{{ galen_version }}.zip"
galen_tmp: "/tmp/galen.zip"

galen_path: /usr/bin/galen
galen_home_path: /opt/galen
# galen_home_path: "~/.galen"

galen_owner: "{{ ansible_ssh_user }}"
galen_group: "{{ ansible_ssh_user }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-galen/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.git](https://galaxy.ansible.com/buluma/git)|[![Ansible Molecule](https://github.com/buluma/ansible-role-git/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-git/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-git.svg)](https://github.com/shadowwalker/ansible-role-git)|
|[buluma.java](https://galaxy.ansible.com/buluma/java)|[![Ansible Molecule](https://github.com/buluma/ansible-role-java/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-java/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-java.svg)](https://github.com/shadowwalker/ansible-role-java)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-galen/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/buluma/alpine)|all|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|Candidate|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-galen/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-galen/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-galen/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
