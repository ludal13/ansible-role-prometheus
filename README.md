prometheus
==========

The present role :
  - installs prometheus server inside a Docker container
  - installs various prometheus exporter
    - node
    - blackbox
    - apache
    - varnish
    - php-fpm
    - opcache
    - redis
    - memcached
    - mysql
    - postgres
    - mongodb
    - opensearch (via plugin for opensearch https://github.com/aiven/prometheus-exporter-plugin-for-opensearch)

Please note that Docker and Haproxy their own embedded exporters.
  - https://docs.docker.com/config/daemon/prometheus/
  - https://www.haproxy.com/fr/blog/haproxy-exposes-a-prometheus-metrics-endpoint/

The role has been successfully tested on :
  - Debian 9
  - Debian 10
  - Debian 11

Forced upgrade of installed exporters can be done by setting the extra parameters "exporter_upgrade" to "yes".

```
ansible-playbook playbook/myhost.yml -t prometheus -e "exporter_upgrade=yes"
```

Role variables
--------------

 - [Variables](docs/variables.md)

Dependencies
------------

  - jq
  - Docker must installed and running for prometheus server

Example Playbook
----------------

    - hosts: prometheus
      ignore_errors: "{{ ansible_check_mode }}" # ignore errors only in check mode !

      roles:
        - { role: brainsys.prometheus, tags: ['prometheus'] }

Example variables
-----------------

    ---
    prometheus_server_enable: 'true'
    prometheus_server_monitor: 'example'

    prometheus_exporter_packages:
      - node
      - mysqld

    prometheus_mysqld_exporter_user: 'foo'
    prometheus_mysqld_exporter_password: 'bar'

    prometheus_node_exporter_targets:
      - server01
      - server02

    prometheus_mysqld_exporter_targets:
      - server01

TODO
----

  - documentation
    - review / enhance documentation
  - memcached
    - add options to exporter launch
      - --memcached.address="localhost:11211"
      - --memcached.timeout=1s
      - --memcached.pid-file=""
    - handle multi instances for memcached exporter

License
-------

GPLv3

Author Information
------------------

Written by Ludovic Cartier <ludovic.cartier@brainsys.io>
