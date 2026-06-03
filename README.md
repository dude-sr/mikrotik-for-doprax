# MikroTik RouterOS in Docker (Doprax)

This project comprises a Docker image that runs a MikroTik's RouterOS virtual machine inside QEMU.



It's designed to simulate MikroTik's RouterOS environment, making it an excellent tool for development and testing purposes, especially for those working with the RouterOS API.



This Docker image is particularly useful for unit testing the routeros-api-php library, allowing developers to test applications in a controlled environment that closely mimics a real RouterOS setup.



For users seeking a fully operational RouterOS environment for production use within Docker, the VR Network Lab project is recommended as an alternative.
credits to EvilFreelancer


## Requirements

- Ubuntu server (amd64)
- `/dev/kvm` recommended for acceptable performance (optional; deploy continues without it, with a warning)

## Access after install

**On the server**

- SSH: `ssh -p 22222 admin@127.0.0.1`
- Web: http://127.0.0.1:7777
- API: `127.0.0.1:8728`

**From your machine** (replace `SERVER_IP` with the host address)

- SSH: `ssh -p 22222 admin@SERVER_IP`
- Web: http://SERVER_IP:7777
- API: `SERVER_IP:8728`

First login: user `admin`, empty password (you will be prompted to set one).

## Related projects

- [evilfreelancer/docker-routeros](https://github.com/EvilFreelancer/docker-routeros) — RouterOS in Docker (QEMU)
- [routeros-api-php](https://github.com/EvilFreelancer/routeros-api-php) — PHP client for the RouterOS API
