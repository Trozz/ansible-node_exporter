node_exporter
=========

Install and Configure [Node Exporter](https://github.com/prometheus/node_exporter)

Requirements
------------

None

Role Variables
--------------

```yaml
# Version to install
node_exporter_version: 0.18.1

# Port for node_exporter to listen
node_exporter_listen_address: ':9100'

# Collectors that are enabled for node_exporter
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

# Installation directory for where to store node_exporter
node_exporter_install_dir: /opt/node_exporter

# URL for GitHub releases
node_exporter_relase_url: "https://github.com/prometheus/node_exporter/releases/download"
# File name for the downloaded file (excluding the archive)
node_exporter_file_name: "node_exporter-{{ node_exporter_version }}.{{ ansible_system|lower }}-{{ 'amd64' if ansible_architecture == 'x86_64' else ansible_architecture|lower }}"
# Compound URL from preivous defaults
node_exporter_download_url: "{{ node_exporter_relase_url }}/v{{ node_exporter_version }}/{{ node_exporter_file_name }}.tar.gz"
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```yaml
    - hosts: servers
      roles:
         - { role: trozz.ansible_node_exporter }
```
License
-------

MIT
