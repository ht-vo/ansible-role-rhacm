# Usage Guide

This document provides detailed instructions on how to use `ansible-role-rhacm`.

## Installation

* Add the following block to your `requirements.yml`:

```yaml
---
- name: rhocp.rhacm
  src: https://github.com/ht-vo/ansible-role-rhacm.git
  version: v1.0.0
...
```

## Playbook

* Create a `playbook.yml`:

```yaml
---
- hosts: localhost
  become: false
  gather_facts: false
  vars:
    rhacm_channel: 'release-2.15'
    rhacm_version: '2.15.1'
    rhacm_install_profile: 'minimal'
  roles:
    - role: rhocp.rhacm
...
```

## Execution Commands

1. **Log in** to your OpenShift cluster.

2. **Install and configure** the operator:

```shell
ansible-playbook ./playbook.yml --tags rhacm_install,rhacm_configure
```

3. **Uninstall** the operator:

```shell
ansible-playbook ./playbook.yml --tags rhacm_uninstall
```
