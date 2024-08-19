<div align="center">
  <br />
    <a href="https://astar.network/" target="_blank">
      <img src="https://repository-images.githubusercontent.com/177367936/60698df1-c1d8-4f3f-8d49-780ea65a04fc" alt="Project Banner">
    </a>
  <br />

  <div>
    <img src="https://img.shields.io/badge/-Ansible-black?style=for-the-badge&logoColor=white&logo=ansible&color=000000" alt="ansible" />
    <img src="https://img.shields.io/badge/-Jinja-black?style=for-the-badge&logoColor=grey&logo=jinja&color=ffffff" alt="jinja" />
  </div>

  <h3 align="center">Ansible Role: Astar</h3>

   <div align="center">
    An Ansible Role that installs an Astar Node on Linux
    </div>
</div>

## 📋 Table of Contents

![Ansible Role](https://img.shields.io/ansible/role/d/asyrafnorafandi/astar?logo=ansible&label=Ansible%20Role%20Downloads&link=https%3A%2F%2Fgalaxy.ansible.com%2Fui%2Fstandalone%2Froles%2Fasyrafnorafandi%2Fastar%2F)
[![Molecule Tests](https://github.com/asyrafnorafandi/ansible-role-astar/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/asyrafnorafandi/ansible-role-astar/actions/workflows/test.yml)
[![Ansible Lint](https://github.com/asyrafnorafandi/ansible-role-astar/actions/workflows/ansible-lint.yml/badge.svg?branch=main)](https://github.com/asyrafnorafandi/ansible-role-astar/actions/workflows/ansible-lint.yml)

1. ⚙️ [Requirements](#requirements)
2. ✅ [Role Variables](#variables)
3. 🔗 [Dependencies](#dependencies)
4. 🚀 [Quick Start](#quick-start)
5. 📜 [License](#license)
6. 🧐 [Author Information](#author)

## ⚙️ <a name="requirements">Hardware requirements</a>

### Astar Network

Bond: 3,200,000 ASTR tokens (3.2M $ASTR)

| Component | Requirement                       |
| --------- | --------------------------------- |
| System    | Ubuntu 22.04                      |
| CPU       | 12 cores - minimum 4 Ghz per core |
| Memory    | 32 GB                             |
| Hard      | Disk 1 TB SSD NVMe                |

### Shiden Network

Bond: 32,000 SDN tokens (32k $SDN)

| Component | Requirement                       |
| --------- | --------------------------------- |
| System    | Ubuntu 22.04                      |
| CPU       | 12 cores - minimum 4 Ghz per core |
| Memory    | 32 GB                             |
| Hard      | Disk 1 TB SSD NVMe                |

## ✅ <a name="variables">Role Variables</a>

| Key                           | Description                                         | Requirement | Default                                 |
| ----------------------------- | --------------------------------------------------- | ----------- | --------------------------------------- |
| swap_enabled                  | To enable swap                                      | optional    | true                                    |
| swap_file_state               | Present / Absent                                    | optional    | present                                 |
| swap_file_size_mb             | Swap Size                                           | optional    | "512"                                   |
| swap_swappiness               | Set swapiness                                       | optional    | "60"                                    |
| swap_file_path                | Directory path to swapfile                          | optional    | /swapfile                               |
| tz_region                     | Server timezone region                              | optional    | Asia/Singapore                          |
| apt_cache_valid_time          | apt cache valid time before expiry                  | optional    | 86400                                   |
| astar_node_user               | Name of user to create for the service              | required    | astar                                   |
| astar_node_name               | Name to run in the astar binary command             | required    | astar-node                              |
| astar_network_chain           | Which network chain to run (astar, shiden, shibuya) | required    | astar                                   |
| astar_telemetry_url           | Telemetry URL                                       | required    | "wss://telemetry.polkadot.io/submit/ 0" |
| astar_data_dir                | Directory path to host Astar data storage           | required    | /var/lib/astar                          |
| astar_client_arch             | Server architecture                                 | required    | x86_64                                  |
| astar_service_state           | State of service (started, stopped)                 | required    | started                                 |
| astar_service_enabled         | To automatically start service on server startup    | required    | true                                    |
| astar_node_type               | Type of node to run (archive, collator, full)       | required    | full                                    |
| astar_collator_state_pruning  | State pruning height                                | optional    | 1000                                    |
| astar_collator_blocks_pruning | Block pruning height                                | optional    | 1000                                    |
| astar_rpc_max_request_size    | RPC Max request size                                | optional    | 1                                       |
| astar_rpc_max_response_size   | RPC Max response size                               | optional    | 1                                       |
| astar_sync_type               | Type of sync to use (full, fast, fast-unsafe, warp) | optional    | warp                                    |
| astar_extra_commands          | List of custom additional parameters to add         | optional    | []                                      |

## 🕸️ <a name="dependencies">Dependencies</a>

```bash
# Install dependencies locally
$ ansible-galaxy install -r requirements.yml
```

Ansible Role dependencies:

- [geerlingguy.swap](https://github.com/geerlingguy/ansible-role-swap)

## 🔗 <a name="quick-start">Quick Start</a>

Running an archive node:

```yaml
- hosts: all
  gather_facts: true
  vars:
    astar_node_type: archive
  roles:
    - asyrafnorafandi.astar
```

Running a full node:

```yaml
- hosts: all
  gather_facts: true
  vars:
    astar_node_type: full
  roles:
    - asyrafnorafandi.astar
```

To run a collator, you must sync in "full" mode. Then you can re-run the playbook in "collator" mode.

```yaml
- hosts: all
  gather_facts: true
  vars:
    astar_node_type: collator
  roles:
    - asyrafnorafandi.astar
```

## 📜 <a name="license">License</a>

MIT / BSD

## 🧐 <a name="author">Author Information</a>

This role was created in 2024 by [Asyraf Norafandi](https://www.github.com/asyrafnorafandi)
