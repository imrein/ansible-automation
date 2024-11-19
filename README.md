# Automation ansible setup

<p align="center">
<img src="https://ansible.readthedocs.io/projects/ansible-core/devel/_static/images/Ansible-Mark-RGB_White.png" width=100>
&nbsp;
<img src="https://www.jenkins.io/images/logos/jenkins/jenkins.svg" width=75>
&nbsp;
<img src="https://gitea.com/assets/img/logo.svg" width=100>
</p>

## Overview

Role to setup an "automation" server. This stack is modular and comes with:

- Jenkins
- Gitea (using MariaDB database)

## Requirements

A machine with an SSH connection.

## Role Variables

The variables are defined in `defaults/main.yml`. These should be configured as needed:

| Variable | Default | Info |
| :------- | :------ | :--- |
| `jenkins_install`               | `true`           | Should Jenkins be installed?                      |
| `jenkins_user`                  | `jenkins`        | User for Jenkins installation                     |
| ---      |         |      |
| `gitea_install`                 | `true`           | Should Gitea be installed?                        |
| `gitea_db_name`                 | `gitea`          | Gitea database name                               |
| `gitea_db_user`                 | `git`            | Gitea database user                               |
| `gitea_db_pass`                 | `git`            | Gitea database password                           |
| `gitea_package_type`            | `linux-amd64`    | Gitea architecture package type                   |
| `lfs_jwt_secret`                | `xxx`            | Gitea lfs_jwt_secret                              |
| `jwt_secret`                    | `xyz`            | Gitea jwt_secret                                  |
| `internal_token`                | `zyx`            | Gitea internal token                              |

## Example playbook

```yml
---
- name: test playbook
  hosts: general

  roles:
  - role: ansible-automation
```
