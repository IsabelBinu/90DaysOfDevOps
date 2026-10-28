Linux commands
- Essential Shell

pwd  - show current directory
ls -lah - list files with details
cd <dir> - change directory
mkdir <dir> -  create a directory
touch <file> - create an empty file
cp <src> <dst> - move or rename
rm <file> -  delete a file
rm  -r <dir> - delete a directory tree
cat <file> - print file contents
mv <src> <dst> - move or rename

- Text and Search

cat <file> - print file contents
less <file> - scroll through a file
grep -R "text" . - search text recursively
find . -name "*.txt" -  find matching files

- System & Processes
df -h -  show disk space
ps aux - list running processes
kill <PID> - stop a process

- Networking

ping example.com - test reachability
ip addr -  show network interfaces
dig example.com -  query DNS records
curl -I https://example.com -  fetch response headers

- Archives

tar -czf files.tar.gz <dir> - create a gzip archive
tar -xzf files.tar.gz -  extract a gzip archive

