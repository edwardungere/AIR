## System notes

### Hardware usage
- `vmstat`/`iostat`: For listing hardware usage such as cpu, i/o, memory
- `df -h`: Disk usage
- `free -h`: Memory usage

### Processes
- `top`: List current proccesses in realtime
- `ps aux`: Display single snapshot of proccesses

### Systemctl
- `systemctl list-units --type=service --all`: List all services
- `systemctl status`
- `systemctl enable`
- `systemctl restart`
- `systemctl disable`
- `journalctl -u`: Service logs

