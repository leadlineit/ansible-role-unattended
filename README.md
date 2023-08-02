# Ansible Galaxy role for install and configure unattended-upgrades.

![Build Status](https://github.com/leadlineit/ansible-role-unattended/actions/workflows/ansible-galaxy-ci.yml/badge.svg)
[![Galaxy Role](https://img.shields.io/badge/Ansible--Galaxy-leadlineit.unattended-blue.svg?logo=ansible&logoColor=white)](https://galaxy.ansible.com/leadlineit/unattended/)

This role helps to for install and configure unattended-upgrades.

Supported OSes
--------------
- Debian 12 (bookworm)
- Debian 11 (bullseye)
- Debian 10 (buster)
- Debian 9 (stretch)

Requirements
------------

This role requires Ansible 2.11 or higher.

Role Variables
--------------

```yaml
---
unattended:
  blacklist:
    - mysql-server
    - php7.3
    - nginx
  options:
    auto_fix_interrupted_dpkg: "true"
    minimal_steps: "true"
    install_on_shutdown: "false"
    mail: "mail@somedomain.com"
    mail_report: "on-change"
    remove_unused_kernel_packages: "true"
    remove_new_unused_dependencies: "true"
    remove_unused_dependencies: "false"
    automatic_reboot: "false"
    automatic_reboot_with_users: "true"
    automatic_reboot_time: "02:00"
    dl_limit: "70"
    sys_log_enable: "false"
    sys_log_facility: "Daemon"
    only_on_ac_power: "true"
    skip_updates_on_metered_connections: "true"
    verbose: "false"
    debug: "false"
    allow_downgrade: "false"
    allow_apt_mark_fallback: "true"
```

The "options" part is optional (please read the documentation about unattended-upgrades before installing any option).
You can skip the "options" part entirely if you don't need to.
Default value for this variables:

```yaml
---
unattended:
  options:
    auto_fix_interrupted_dpkg: "true"
    minimal_steps: "true"
    install_on_shutdown: "false"
    mail: "mail@somedomain.com"
    mail_report: "on-change"
    remove_unused_kernel_packages: "true"
    remove_new_unused_dependencies: "true"
    remove_unused_dependencies: "false"
    automatic_reboot: "false"
    automatic_reboot_with_users: "true"
    automatic_reboot_time: "02:00"
    dl_limit: "70"
    sys_log_enable: "false"
    sys_log_facility: "Daemon"
    only_on_ac_power: "true"
    skip_updates_on_metered_connections: "true"
    verbose: "false"
    debug: "false"
    allow_downgrade: "false"
    allow_apt_mark_fallback: "true"
```

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - { role: leadlineit.unattended, tags: unattended }
```

License
-------

BSD

Author Information
------------------

This role was created by Artem Kasianchuk.
