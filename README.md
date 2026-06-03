# MikroTik RouterOS in Docker (Doprax)

Doprax app for installing MikroTik RouterOS on **Ubuntu** using Docker.

It runs [evilfreelancer/docker-routeros](https://github.com/EvilFreelancer/docker-routeros) — a MikroTik CHR virtual machine inside QEMU/Docker — so you get a RouterOS environment on your server without bare-metal hardware.

Useful for development and testing, especially with [routeros-api-php](https://github.com/EvilFreelancer/routeros-api-php), which talks to RouterOS over the API in a setup that closely matches a real device.

**Repository:** https://github.com/dude-sr/mikrotik-for-doprax

## Requirements

- Ubuntu server (amd64)
- `/dev/kvm` recommended for acceptable performance (optional; deploy continues without it, with a warning)

## Access after install

| Service | On server | Remote |
|---------|-----------|--------|
| SSH | `ssh -p 22222 admin@127.0.0.1` | `ssh -p 22222 admin@SERVER_IP` |
| Web | http://127.0.0.1:7777 | http://SERVER_IP:7777 |
| API | `127.0.0.1:8728` | `SERVER_IP:8728` |

First login: user `admin`, empty password (set when prompted).

## Related projects

- [evilfreelancer/docker-routeros](https://github.com/EvilFreelancer/docker-routeros) — RouterOS in Docker (QEMU)
- [routeros-api-php](https://github.com/EvilFreelancer/routeros-api-php) — PHP client for the RouterOS API
