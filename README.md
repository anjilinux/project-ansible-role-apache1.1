[![Build Status](https://travis-ci.org/inmotionhosting/ansible-role-apache.png?branch=master)](https://travis-ci.org/inmotionhosting/ansible-role-apache) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-apache.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-apache/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-apache.svg)](https://github.com/inmotionhosting/ansible-role-apache/stargazers)

# Ansible Role: Apache
Modular Ansible Role for deploying and configuring Apache

## Requirements
This Ansible role supports the two latest stable releases of specific
server-focused Linux distributions and aims to follow their deprecation
policies. Additionally we will focus on supporting the latest two stable
releases of each, which at the time of writing are as follows:

* CentOS 7, 8
* Debian 10, 11
* Ubuntu 18.04, 20.04

## Dependencies
None.

## Role Variables
Available variables are listed below with their default values (you can also see `defaults/main.yml`)

| Variable                   | Description |
| -------------------------- | ----------- |
| apache_name                | Default: `httpd`
| apache_daemon              | Default: `httpd`
| apache_user                | Default: `apache`
| apache_group               | Default: `apache`
| apache_port_http           | Default: `80`
| apache_port_https          | Default: `443`
| apache_config              | Default: `/etc/{{ apache_name }}/conf/{{ apache_name }}.conf`
| apache_config_path         | Default: `/etc/{{ apache_name }}/conf.d`
| apache_config_ports        | Default: `{{ apache_config_path }}/ssl.conf`
| apache_config_site_path    | Default: `{{ apache_config_path }}`
| apache_modules_path        | Default: `/etc/{{ apache_name }}/modules`
| apache_modules_config_path | Default: `/etc/{{ apache_name }}/conf.modules.d`
| apache_packages            | The list of Apache packages to install
| apache_systemd_restart     | Default: `false`

## Example Playbook
```yaml
- hosts: www
  roles:
    - role: inmotionhosting.apache
```

## License
GPLv3

## Author Information
[InMotion Hosting](https://inmotionhosting.com)
