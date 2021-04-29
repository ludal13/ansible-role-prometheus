prometheus
==========

The present role :
  - installs prometheus server inside a Docker container
  - installs various prometheus exporter

It has been tested on :
  - Debian 9
  - Debian 10

Role variables
--------------

| Variable                           | Type    | Choices      | Default                                                                       | Comment                                                                    |
|------------------------------------|---------|--------------|-------------------------------------------------------------------------------|----------------------------------------------------------------------------|

Dependencies
------------

Docker must installed and running.

Example Playbook
----------------

    - hosts: prometheus
      ignore_errors: "{{ ansible_check_mode }}" # ignore errors only in check mode !

      roles:
        - { role: brainsys.prometheus, tags: ['prometheus'] }

Example variables
-----------------

    --- 
    prometheus_enable: 'true'
    prometheus_node_exporter_enable: 'true'
    prometheus_mysqld_exporter_enable: 'true'
    prometheus_mysqld_exporter_user: 'foo'
    prometheus_mysqld_exporter_password: 'bar'

TODO
----

License
-------

GPLv3

Author Information
------------------

Written by Ludovic Cartier <ludovic.cartier@brainsys.io>
