# Ansible Role: ansible-apps_sensu


## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_sensu.svg?branch=master?style=flat)](https://travis-ci.com/lotusnoir/ansible-apps_sensu)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_sensu-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_sensu)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_sensu?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_sensu)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_sensu.svg)](https://github.com/lotusnoir/ansible-apps_sensu/releases/)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_sensu&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_sensu)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_sensu&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_sensu)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_sensu&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_sensu)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_sensu&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_sensu)

Deploy [sensu-core](https://docs.sensu.io/sensu-core/latest/) monitoring system using ansible.

## Requirements

none

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `sensu_client_name` | test | sensu client name |
| `sensu_client_port` | 3030| sensu client port |
| `sensu_client_bindaddress` | 0.0.0.0| client address to listen |
| `sensu_redis_host` | 127.0.0.1 | redis host address |
| `sensu_redis_port` | 6379 | redis port address |
| `sensu_transport` | redis | transport protocol to use |
| `sensu_uchiwa_port` | 3080 | uchiwa port |
| `sensu_admin_passwd` | "" | sensu admin password |
| `sensu_uchiwa_admin_passwd` | "" | uchiwa web admin password |
| `sensu_users_list` | "" | add users to acces uchiwa |

## Examples

	---
	- hosts: apps_sensu
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_sensu
	  vars:
        sensu_admin_passwd: "strongpass1"
        sensu_uchiwa_admin_passwd: "strongpass2"
        sensu_users_list: ""
          - { name: "test", passwd: "password", readonly: 'true' }
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
