Role Name
=========

An Ansible role to configure libvirt networks.

Requirements
------------

A libvirt deployment.

Role Variables
--------------

TODO:
A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

This role uses the Ansible Core maintened virt module.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - vars:
        networks:
          - name: test
            forward:
              mode: nat
              port:
                start: 1025
                end: 65535
            bridge:
              name: virbr3
              stp: on
              delay: 0
            hwaddr: 52:54:00:f7:34:54
            domainname: internal
            ipaddr: 192.168.126.2
            netmask: 255.255.255.0
            dhcp_range:
              start: 192.168.126.2
              end: 192.168.126.253

    - hosts: servers
      roles:
         - { role: jfenal.ansible-role-virt-net, networks: networks }

License
-------

BSD

Author Information
------------------

Jérôme Fenal <jfenal@redhat.com>
@jfenal
