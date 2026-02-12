# [Ansible role galen](#ansible-role-galen)

Automated testing of look and feel for your responsive websites.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-galen/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-galen/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-galen/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-galen)|[![downloads](https://img.shields.io/ansible/role/d/buluma/galen)](https://galaxy.ansible.com/buluma/galen)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-galen.svg)](https://github.com/buluma/ansible-role-galen/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-galen/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  pre_tasks:
    - name: Update apt cache.
      apt: update_cache=true cache_valid_time=600
      when: ansible_os_family == 'Debian'
  tasks:
    - name: "Install Git"
      ansible.builtin.include_role:
        name: "buluma.git"
    - name: "Install Java"
      ansible.builtin.include_role:
        name: "buluma.java"

    - name: "Include buluma.galen"
      ansible.builtin.include_role:
        name: "buluma.galen"
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-galen/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: false
  become: true

  roles:
    - name: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-galen/blob/master/defaults/main.yml):

```yaml
---
# defaults file for galen

galen_packages:
  - unzip

galen_version: "2.4.4"
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

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.git](https://galaxy.ansible.com/buluma/git)|[![Build Status GitHub](https://github.com/buluma/ansible-role-git/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-git/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-git/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-git)|
|[buluma.java](https://galaxy.ansible.com/buluma/java)|[![Build Status GitHub](https://github.com/buluma/ansible-role-java/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-java/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-java/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-java)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-galen/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/buluma/alpine)|all|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-galen/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-galen/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

