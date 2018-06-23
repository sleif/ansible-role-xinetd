# ansible-role-xinetd

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-xinetd.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-xinetd)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-xinetd-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/xinetd)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Extended Internet daemon

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    xinetd_defaults_bind: '0.0.0.0'
    xinetd_defaults_cps: '50 10'
    xinetd_defaults_groups: true
    xinetd_defaults_instances: 50
    xinetd_defaults_only_from: ''
    xinetd_defaults_max_load: ''
    xinetd_defaults_no_access: ''
    xinetd_defaults_passenv: ''
    xinetd_defaults_per_source: 10
    xinetd_defaults_log_type:
      - SYSLOG
      - daemon
      - info
    xinetd_defaults_log_on_failure:
      - HOST
    xinetd_defaults_log_on_success:
      - PID
      - HOST
      - DURATION
      - EXIT
    xinetd_defaults_mdns: false
    xinetd_defaults_umask: '002'
    xinetd_defaults_v6only: false
    xinetd_extraoptions: ''
    xinetd_includedir: /etc/xinetd.d
    xinetd_lang: en_US

You can define global banners by using the variables below, base64 encoded.

    xinetd_defaults_banner: |
      YmFubmVyCg==
    xinetd_defaults_banner_fail: |
      YmFubmVyX2ZhaWwK
    xinetd_defaults_banner_success: |
      YmFubmVyX3N1Y2Nlc3MK

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.xinetd

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
