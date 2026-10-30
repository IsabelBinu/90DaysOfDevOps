Processes
1. ps aux - It shows all running processes
2. top - Live view of CPU, memory, and running processes

Services
1. systemctl status ssh - Checks whether the ssh service is running
2. systemctl list-units --type=service - Lists currently active services

Logs
1. journalctl -u nginx  - shows logs for nginx service
2. tail -n 50 /var/log/syslog - shows the latest 50 system log lines

