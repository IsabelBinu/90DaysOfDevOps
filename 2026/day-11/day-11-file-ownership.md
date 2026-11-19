# Linux DevOps – Ownership & Group Management

### Task 1: Understanding Ownership
```bash
ls -l
```
**Observation:** Owner is the user who owns the file, while group represents users who can share access through group permissions.

### Task 2: Change File Owner
```bash
touch devops-file.txt
sudo chown tokyo devops-file.txt
sudo chown berlin devops-file.txt
ls -l devops-file.txt
```
**Observation:** `chown` changes the owner of a file.

### Task 3: Change File Group
```bash
touch team-notes.txt
sudo groupadd heist-team
sudo chgrp heist-team team-notes.txt
ls -l team-notes.txt
```
**Observation:** `chgrp` changes the group ownership of a file.

### Task 4: Change Owner & Group Together
```bash
touch project-config.yaml
sudo chown professor:heist-team project-config.yaml

mkdir app-logs
sudo chown berlin:heist-team app-logs

ls -l project-config.yaml
ls -ld app-logs
```
**Observation:** `chown owner:group` changes both the owner and group.

### Task 5: Recursive Ownership
```bash
mkdir -p heist-project/{vault,plans}
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf

sudo groupadd planners
sudo chown -R professor:planners heist-project/
ls -lR heist-project/
```
**Observation:** `chown -R` changes ownership of a directory and everything inside it.

### Task 6: Practice Challenge
```bash
sudo groupadd vault-team
sudo groupadd tech-team

mkdir bank-heist
touch bank-heist/{access-codes.txt,blueprints.pdf,escape-plan.txt}

sudo chown tokyo:vault-team bank-heist/access-codes.txt
sudo chown berlin:tech-team bank-heist/blueprints.pdf
sudo chown nairobi:vault-team bank-heist/escape-plan.txt

ls -l bank-heist/
```
**Observation:** Files within the same directory can have different owners and groups.

### What I Learned
Practised Linux file ownership and group management using `chown`, `chgrp`, and `chown -R`.

- `chown` → Changes file owner.
- `chgrp` → Changes file group.
- `chown owner:group` → Changes both.
- `-R` → Applies ownership changes recursively.
- `ls -l` → Verifies ownership and permissions.

**Key takeaway:** `chown` and `chgrp` manage ownership, while `chmod` manages file permissions.