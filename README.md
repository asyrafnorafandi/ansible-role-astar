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

![GitHub Sponsors](https://img.shields.io/github/sponsors/asyrafnorafandi)

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

None.

## 🕸️ <a name="dependencies">Dependencies</a>

```bash
# Install dependencies locally
$ ansible-galaxy install -r requirements.yml
```

Ansible Role dependencies:

- [geerlingguy.swap](https://github.com/geerlingguy/ansible-role-swap)

## 🔗 <a name="quick-start">Quick Start</a>

```yaml
- hosts: all
  roles:
    - asyrafnorafandi.astar
```

## 📜 <a name="license">License</a>

MIT / BSD

## 🧐 <a name="author">Author Information</a>

This role was created in 2024 by [Asyraf Norafandi](https://www.github.com/asyrafnorafandi)
