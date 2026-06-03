# MikroTik RouterOS in Docker (Doprax)

Ansible playbook to deploy [evilfreelancer/docker-routeros](https://github.com/EvilFreelancer/docker-routeros) on Ubuntu with Docker Compose.

Designed for development and testing (e.g. [routeros-api-php](https://github.com/EvilFreelancer/routeros-api-php)). For production-like RouterOS in Docker, see [vrnetlab](https://github.com/plajjan/vrnetlab).

**Repository:** https://github.com/dude-sr/mikrotik-for-doprax

## Requirements

- Ubuntu target host (amd64)
- Ansible + `community.docker` collection on the control machine
- `/dev/kvm` recommended (optional; playbook warns if missing)

## Quick start

```bash
ansible-galaxy collection install community.docker

cat > hosts <<'EOF'
YOUR_SERVER_IP ansible_user=root
EOF

ansible-playbook -i hosts playbook.yaml --ask-pass
# use --ask-become-pass if sudo is required
```

## What the playbook does

- Installs Docker CE and compose plugin
- Installs Python `docker` SDK in a venv (Ubuntu 24.04 safe)
- Deploys compose with **two Docker networks** (required for SSH/web from host — see upstream README)
- Optionally passes `/dev/kvm` when present
- Verifies container + SSH port, prints deployment summary

## Access after deploy

| Service | On server | Remote |
|---------|-----------|--------|
| SSH | `ssh -p 22222 admin@127.0.0.1` | `ssh -p 22222 admin@SERVER_IP` |
| Web | http://127.0.0.1:7777 | http://SERVER_IP:7777 |
| API | `127.0.0.1:8728` | `SERVER_IP:8728` |

First login: user `admin`, empty password (set when prompted).

## Credits

- [EvilFreelancer/docker-routeros](https://github.com/EvilFreelancer/docker-routeros)
