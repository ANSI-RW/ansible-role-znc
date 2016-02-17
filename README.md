# Ansible Role: ZNC

[![Build Status](https://img.shields.io/travis/ANSI-RW/ansible-role-znc.svg)](https://travis-ci.org/ANSI-RW/ansible-role-znc) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/ANSI-RW/ansible-role-znc/master/LICENSE)

Installs and configures ZNC on RHEL/CentOS ~~or Debian/Ubuntu~~.

## Requirements

- The EPEL repository on RHEL/CentOS. (try https://github.com/ANSI-RW/ansible-role-repo-remi)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
znc_conf_use_template: true

znc_conf_listener_port: 1025
znc_conf_listener_ipv4: true
znc_conf_listener_ipv6: true
znc_conf_listener_ssl: false

znc_conf_user_username: admin
# Used by "znc --makepass"
znc_conf_user_password: hackme
znc_conf_user_ident: admin
znc_conf_user_nick: admin
znc_conf_user_realname: Got ZNC?
```

## Dependencies

None

## Example Playbook

```yaml
- hosts: servers

  vars_files:
    - vars/main.yml

  roles:
    - role: ansible-role-repo-remi # RHEL/CentOS
    - role: ansible-role-znc
```

Inside `vars/main.yml`:

```yaml
znc_conf_listener_port: 1337
znc_conf_user_password: "[secure password]"

# ... etc ...
```

## License

MIT
