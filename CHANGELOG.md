# Changelog

## 2026-06-03

- Two-network Docker Compose (`default` + `routeros_net`) for working SSH/telnet/web from host
- Optional `/dev/kvm` in compose when device exists
- Python Docker SDK installed in venv (PEP 668 / Ubuntu 24.04)
- Post-deploy health check and formatted summary (`templates/deployment_summary.j2`)
- KVM warning in summary (no abort)
