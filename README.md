# Ansible role for NewRelic

[![Build Status](https://travis-ci.org/torian/ansible-role-newrelic.svg)](https://travis-ci.org/torian/ansible-role-newrelic)

This ansible role installs [NewRelic Sysmond](https://newrelic.com/) client.

## Supported Platforms
  * EL / Centos (6 / 7)
  * Debian (Wheezy / Jessie)
  * Ubuntu (Trusty)
  * AMZ Linux

## Role Variables

The following role variables are defined in `defaults/main.yml`, and are
probably the only ones you will want to change. For a detailed explanation
about them you can take a look at the file.

```
newrelic_license_key: false
newrelic_sysmond_loglevel: info
newrelic_sysmond_labels: false
```

## Usage

The only ansible variable to be defined is actually `newrelic_license_key`. If
this one is not defined, then the role will fail with a message.

An example of the usage of this role is:

```
---
- hosts: all

  vars:
    newrelic_license_key: 'abcdefghijk123456789'

  roles:
    - { role: torian.newrelic }
```

