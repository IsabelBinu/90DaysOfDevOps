Processes/services: 
- Check status and recent Nginx logs:
ps aux --sort=-%cpu | head -n 6
systemctl status nginx --no-pager
sudo journalctl -u nginx -n 20 --no-pager



File practice:
mkdir -p ~/day12-revision-lab && cd ~/day12-revision-lab
echo "First line" > notes.txt
echo "Second line" >> notes.txt
cp notes.txt copy.txt
chmod 640 notes.txt
ls -l notes.txt copy.txt
Checkpoint: > overwrites, >> appends; 640 = owner rw, group r, others none.

5 incident commands: systemctl status, journalctl -u, ss -tlnp, curl -sSI, df -h.

Users/groups:id tokyo
getent group developers
touch ~/day12-revision-lab/owner-demo.txt
sudo chown tokyo:developers ~/day12-revision-lab/owner-demo.txt
ls -l ~/day12-revision-lab/owner-demo.txt

Checkpoint: Run chown only if the user/group exist. chown changes ownership; chmod changes permissions.