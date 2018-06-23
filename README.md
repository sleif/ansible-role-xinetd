# ansible-role-xinetd

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-xinetd.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-xinetd)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-xinetd-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/xinetd)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Extended Internet daemon

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    xinetd_banners: {}
    xinetd_d: {}
    xinetd_defaults:
      bind: 0.0.0.0
      cps: '50 10'
      groups: true
      instances: 50
      log_on_failure:
        - HOST
      log_on_success:
        - PID
        - HOST
        - DURATION
        - EXIT
      log_type: 'SYSLOG daemon info'
      mdns: false
      per_source: 10
      umask: 002
      v6only: false
    xinetd_extraoptions: ''
    xinetd_includedir: /etc/xinetd.d
    xinetd_lang: en_US
    xinetd_packages: []

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.xinetd
          xinetd_banners:
            banner: |
              YmFubmVyCg==
            banner_fail: |
              YmFubmVyX2ZhaWwK
            banner_success: |
              YmFubmVyX3N1Y2Nlc3MK
          xinetd_d:
            rsh:
              disable: true
              socket_type: stream
            telnet:
              disable: true
              socket_type: stream
          xinetd_defaults:
            banner: /etc/xinetd.banner
            banner_fail: /etc/xinetd.banner_fail
            banner_success: /etc/xinetd.banner_success
            bind: 0.0.0.0
            cps: '50 10'
            groups: true
            instances: 50
            log_on_failure:
              - HOST
            log_on_success:
              - PID
              - HOST
              - DURATION
              - EXIT
            log_type: 'SYSLOG daemon info'
            mdns: false
            per_source: 10
            umask: 002
            v6only: false
          xinetd_packages:
            - telnet

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
