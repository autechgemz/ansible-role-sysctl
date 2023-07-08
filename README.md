# Ansible Role: sysctl

## Description

Manage sysctl kernel parameters.

## Requirements

None

## Dependencies

None

## OS Platforms

- Debian os_family
- Redhat os_family

## Example Playbook

```
- hosts: all
  roles:
    - sysctl
```

## Role Variables

### sysctl_config_options: (dict)

```
sysctl_config_options: {}

# name:
#   value: ...
#   state: present|absent
```

### sysctl_dropin_config_options: (dict)

```
sysctl_dropin_config_options: {}

# name:
#   file: ...
#   value: ...
#   state: present|absent
```

### sysctl_dropin_config_purge: (bool)

```
sysctl_dropin_config_purge: false
```

### sysctl_config_reload: (bool)

```
sysctl_config_reload: true
```

### sysctl_config_persistent: (bool)

```
sysctl_config_persistent: true
```

## Example vars

```
sysctl_config_options:
  net.ipv4.ip_forward:
    value: 0
    state: present
  vm.stat_interval:
    value: 1
    state: present

sysctl_dropin_config_options:
  vm.stat_interval:
    file: 99-ansible.conf
    value: 1
    state: present
  vm.swappiness:
    file: 98-ansible.conf
    value: 30
    state: present
```
