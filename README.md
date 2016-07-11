# ansible-role-xinetd

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-xinetd.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-xinetd)

RHEL/CentOS - Extended Internet daemon

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    xinetd_defaults_cps: [ '50', '10' ]
    xinetd_defaults_groups: True
    xinetd_defaults_instances: 50
    xinetd_defaults_per_source: 10
    xinetd_defaults_log_type: [ 'SYSLOG', 'daemon', 'info' ]
    xinetd_defaults_log_on_failure: [ 'HOST' ]
    xinetd_defaults_log_on_success: [ 'PID', 'HOST', 'DURATION', 'EXIT' ]
    xinetd_defaults_umask: '002'
    xinetd_defaults_v6only: False
    xinetd_extraoptions: ''
    xinetd_includedir: /etc/xinetd.d
    xinetd_xinetd_lang: en_US

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.xinetd

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
