# Ansible role - `system_autoupdate`

Manage hosts auto update mechanisms.

⚠️ **This role has been moved into the collection [jpclipffel.system](https://github.com/jpclipffel/ansible_collection.system):**
* GitHub: https://github.com/jpclipffel/ansible_collection.system
* Ansible Galaxy: https://galaxy.ansible.com/jpclipffel/system

---

The following operating systems are supported:

| System  | Distribution | Version | Notes                      |
|---------|--------------|---------|----------------------------|
| `linux` | `ubuntu`     | -       | Tested on `18.04`, `20.04` |

## Tags

| Tag        | Description                                          |
|------------|------------------------------------------------------|
| `setup`    | Setup the host auto-update mechanisms                |
| `teardown` | Deactive the hosts auto-update                       |
| `remove`   | Deactive and remove the hosts auto-update mechanisms |

## Variables

| Variable                                     | Type            | Required | Defaut                                      | Description |
|----------------------------------------------|-----------------|----------|---------------------------------------------|-------------|
| `system_autoupdate_unattended_upgrades_file` | `string` (path) | No       | `/etc/apt/apt.conf.d/50unattended-upgrades` | -           |
| `system_autoupdate_auto_upgrades_file`       | `string` (path) | No       | `/etc/apt/apt.conf.d/20unattended-upgrades` | -           |

## Templates

| Template                 | Description                                  |
|--------------------------|----------------------------------------------|
| `unattended-upgrades.j2` | APT's unattended upgrades configuration file |
| `auto-upgrades.j2`       | APT's auto upgrades configuration file       |

## Tasks

```text
main.yml
|
| -------------- tags: always -------------------------------------------------
|
\__ linux_<distribution>.yml
```
