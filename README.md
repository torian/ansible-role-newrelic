# Ansible role for NewRelic

[![Build Status](https://travis-ci.org/torian/ansible-role-newrelic.svg)](https://travis-ci.org/torian/ansible-role-newrelic)

This ansible role installs [NewRelic Sysmond](https://newrelic.com/) client.

## Supported Platforms
  * EL / Centos (6 / 7)
  * Debian (Wheezy / Jessie)
  * Ubuntu (Trusty)
  * AMZ Linux

## Role Variables

The following default vars are probably the only ones that should be modified:

```
newrelic_upgrade: false
newrelic_license_key: false
newrelic_sysmond_labels: false
newrelic_sysmond_hostname: # undefined
```

APM settings:

```
newrelic_apm_enabled: false

newrelic_apm_config_defaults:
  monitor_mode: 'true'
  log_level: info
  ssl: 'true'
  high_security: 'false'
  transaction_tracer.enabled: 'true'
  transaction_tracer.transaction_threshold: apdex_f
  transaction_tracer.record_sql: obfuscated
  transaction_tracer.stack_trace_threshold: 0.5
  transaction_tracer.explain_enabled: 'true'
  transaction_tracer.explain_threshold: 0.5
  transaction_tracer.function_trace: ''
  error_collector.enabled: 'true'
  error_collector.ignore_errors: ''
  browser_monitoring.auto_instrument: 'true'
  thread_profiler.enabled: 'true'

newrelic_apm_config: {}
```

The variables `newrelic_apm_config_defaults` and `newrelic_apm_config` will
be merged using the jinja2 filter `combine()`.

## Usage

The only variable taht you need to defin is actually `newrelic_license_key`. If
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

If you need to upgrade the newrelic client, you can set to `newrelic_upgrade: true`.
