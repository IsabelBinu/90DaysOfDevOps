 Task 1: Create Users
    sudo useradd -m -s /bin/bash tokyo
    sudo useradd -m -s /bin/bash berlin
    sudo useradd -m -s /bin/bash professor
useradd -m creates the account and its home directory
Sets the account password -    sudo passwd tokyo

getent passwd tokyo berlin professor
ls -ld /home/tokyo /home/berlin /home/professor

getent passwd checks the system account database

Task2: Create Groups
    sudo groupadd developers
    sudo groupadd admins
    getent group developers admins

groupadd creates a group, while getent group verifies its entry in the system group database

Task 3 : Assign users to groups

sudo usermod -aG developers tokyo
sudo usermod -aG developers,admins berlin
sudo usermod -aG admins professor


id tokyo
id berlin
id professor

usermod -aG appends supplementary groups. Omitting -a can remove a user's existing supplementary memberships. id shows the primary and supplementary groups.

Task 4: Shared Directory

sudo mkdir -p /opt/dev-project
sudo chgrp developers /opt/dev-project
sudo chmod 775 /opt/dev-project

ls -ld /opt/dev-project

sudo -u tokyo touch /opt/dev-project/tokyo.txt
sudo -u berlin touch /opt/dev-project/berlin.txt

ls -l /opt/dev-project

chgrp assigns the directory's group owner; chmod 775 allows the owner and group to read/write/enter, while others can read/enter but not create files. The sudo -u ... touch commands verify real group access rather than relying on root access.

Task 5

sudo useradd -m -s /bin/bash nairobi (Create user with home directory and Bash shell)
sudo passwd nairobi (Set or change a user's password interactively)
sudo groupadd project-team (create a group)
sudo usermod -aG project-team nairobi (Append a supplementary group membership)
sudo usermod -aG project-team tokyo

sudo mkdir -p /opt/team-workspace (Create a directory)
sudo chgrp project-team /opt/team-workspace (Change group ownership)
sudo chmod 775 /opt/team-workspace (Set directory permissions to rwxrwxr-x)

# Verify user memberships and directory permissions
id nairobi (Show a user's IDs and group memberships)
id tokyo
ls -ld /opt/team-workspace(Inspect home directory existence, permissions, and ownership)
stat -c '%a %A %U:%G %n' /opt/team-workspace (Check numeric and symbolic modes and ownership)

# Test file creation without root privileges
sudo -u nairobi touch /opt/team-workspace/nairobi.txt (Test whether a particular user can create a file)
ls -l /opt/team-workspace (List created files and their ownership)