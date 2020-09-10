# Ansible Role: apps_sensu


## Description

[![Build Status](https://travis-ci.com/lotusnoir/apps_sensu.svg?branch=master)](https://travis-ci.com/lotusnoir/apps_sensu)[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__sensu-blue)](https://galaxy.ansible.com/lotusnoir/apps_sensu/)[![GitHub tag](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/apps_sensu/tags)

Deploy sensu monitoring system using ansible.

## Requirements

none

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `sensu_client_name` | test |  |
| `sensu_client_port` | 3030|  |
| `sensu_client_bindaddress` | 0.0.0.0|  |
| `sensu_redis_host` | 127.0.0.1 |  |
| `sensu_redis_port` | 6379 |  |
| `sensu_transport` | redis |  |
| `sensu_uchiwa_port` | 3080 |  |
| `sensu_admin_passwd` | "" |  |
| `sensu_uchiwa_admin_passwd` | "" |  |
| `sensu_users_list` | "" |  |

## Examples

	---
	- hosts: apps_sensu
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: apps_sensu
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

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
