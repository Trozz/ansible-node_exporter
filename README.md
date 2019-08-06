node_exporter
=========

Install and Configure [Node Exporter](https://github.com/prometheus/node_exporter)

Requirements
------------

None

Role Variables
--------------

```
node_exporter_version: 0.18.1
node_exporter_listen_address: ':9100'
node_exporter_collectors:
  - filesystem
  - netdev
  - cpu
  - diskstats
  - mdadm
  - loadavg
  - time
  - uname
  - logind


node_exporter_install_dir: /opt/node_exporter
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: trozz.node_exporter }

License
-------

MIT
