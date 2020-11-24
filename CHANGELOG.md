# Changelog

## 2020-11-24: 0.5.1

  - Fix iteritems() no longer present in python 3

## 2019-10-15: 0.5.0

  - Removed deprecated NR Sysmond

## 2017-05-25: 0.4.0

  - APM settings (vars newrelic_apm_config_defaults & newrelic_apm_config)

## 2017-03-17: 0.3.2

  - Ansible lint - Fixed trailing whitespaces

## 2017-02-16: 0.3.1

  - fix for empty labels. If `newrelic_sysmond_labels` contains
    an attribute with an empty value, the label will be skipped

## 2016-04-01: 0.3.0

  - Porting functionality to comply with Ansible 2.x changes
    complex vars

## 2016-03-16: 0.2.0

  - Add sysmond hostname (newrelic_sysmond_hostname)
  - Documentation

## 2016-03-15: 0.1.0

  - Tests for TravisCI
  - Vagrant tests
  - Centos / RedHat support
