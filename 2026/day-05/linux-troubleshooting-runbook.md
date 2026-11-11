- Environment

1. uname -a : Linux kernel and architecture identified
2. cat /etc/os-release : PRETTY_NAME="Ubuntu 26.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04.1 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute


- Filesystem

1. mkdir -p /tmp/runbook-demo - Creates a directory, -p prevents an error if the directory alrerady exists
2. cp /etc/hosts /tmp/runbook-demo/hosts-copy - copies the file from original to destiantion
3. ls -l /tmp/runbook-demo/hosts-copy - verify the copied file
4. mkdir -p /tmp/runbook-demo && cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo/hosts-copy - Run evrything in a single command. && operator means execute the next command only if the previous command suceeds.

- CPU

1. ps -o pid,pcpu,pmem,comm - To check the process id, CPU usage, memory usage and process name of a specific running process
PID %CPU %MEM COMMAND
   3190  0.0  0.5 bash
   3263  0.0  0.4 ps
2. ps -o pid,pcpu,pmem,comm -p 453 - Displays the information only for process id 453

- Memory

1. free -h - To check the memory availability
               total        used        free      shared  buff/cache   available
Mem:           908Mi       323Mi        92Mi       2.7Mi       609Mi       585Mi
Swap:             0B          0B          0B

- Disk
1. df -h /tmp - Filesystem capacity and free spaces checked for /tmp
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           455M  4.0K  455M   1% /tmp
2. du -sh /home/ubuntu - Disk usage for the particular directory
72K     /home/ubuntu
(**Note** df is for the disk free and du is for the disk usage)

- Network
1. ss -tulpn - display network sockets and identify which services are listening on which ports
Netid             State              Recv-Q             Send-Q                               Local Address:Port                           Peer Address:Port             Process             
udp               UNCONN             0                  0                                        127.0.0.1:323                                 0.0.0.0:*                                    
2. curl -sSI http://localhost - to check the HTTP response headers of a website or service without downloading its response body.
HTTP/1.1 200 OK
Server: nginx/1.28.3 (Ubuntu)
Date: Tue, 10 Nov 2026 02:38:43 GMT
Content-Type: text/html
Content-Length: 13923
Last-Modified: Mon, 26 Oct 2026 23:05:17 GMT
Connection: keep-alive
ETag: "6adfdcad-3663"
Accept-Ranges: bytes

- Logs
1. journalctl -u runbook-demo -n 50 --no-pager - Display the latest 50 log entries for a specific systemd service named runbook-demo.
(--no-pager) - Disables pagination
-- No entries --
2. tail -n 50 /var/log/syslog - displays the last 50 lines of a log file
