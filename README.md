# awx-ar

Ansible role for installing AWX with Docker and systemd.

## Description

This role installs [AWX](https://github.com/ansible/awx) using Docker containers managed by systemd. It provides:

- AWX web application
- Redis for task queue
- Receptor worker for job execution
- PostgreSQL database integration

## Requirements

- Docker
- systemd
- PostgreSQL (managed externally or via another role)

## Role Variables

See `defaults/main.yml` for all available variables.

### Required variables:

```yaml
awx_enabled: true
awx_hostname: awx.example.com
awx_admin_user: admin
awx_admin_password: "your-secure-password"
```

## Dependencies

- postgres role (for database)

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: awx-ar
      awx_enabled: true
      awx_hostname: awx.example.com
      awx_admin_password: "secure-password"
```

## License

AGPL-3.0-or-later
