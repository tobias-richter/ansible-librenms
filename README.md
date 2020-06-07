# tobias_richter.librenms

[![Build Status](https://travis-ci.org/tobias-richter/ansible-librenms.svg?branch=master)](https://travis-ci.org/tobias-richter/ansible-librenms)

This role installs and configures librems.

This role supports configuring
* `ignore_mount`
* `ignore_mount_regexp`
* rrdcached
* poller threads
* baseurl and domain
* nets
* snmp (community, authname etc. at the moment only authPriv is
  `supported`)
* proxmox
* influxdb
* ldap

The default credentials for the installation are `admin` / `admin`.

Have a look at
[tobias_richter.rrdcached](https://galaxy.ansible.com/tobias_richter/rrdcached)
for setting up rrdcached on your server.

## Requirements

This role requires Ansible 2.7 or higher.

## Role Variables

See [defaults/main.yml](defaults/main.yml) for the documented role variables.
See also the distribution specific [vars](vars).

Mandadtory variables are:
* `librenms_sql_db_password`

## Example Playbook

This playbook setups librenms.

    - hosts: apt_config
	  roles:
	    - role: tobias_richter.librenms
    librenms_sql_db_password: librenmsdbpassword 