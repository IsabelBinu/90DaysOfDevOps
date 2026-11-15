# Linux File Management & Permissions

### Task 1: Create Files
```bash
mkdir ~/file-permissions-lab
cd ~/file-permissions-lab
touch devops.txt
vim notes.txt
vim script.sh
ls -l
```
Added `echo "Hello DevOps"` to `script.sh`.

**Observation:** Created three files successfully.

### Task 2: Read Files
```bash
cat notes.txt
vim -R script.sh
head -n 5 /etc/passwd
tail -n 5 /etc/passwd
```
**Observation:** `cat` reads the full file, `head` shows the first lines, and `tail` shows the last lines.

### Task 3: Understand Permissions
```bash
ls -l devops.txt notes.txt script.sh
```
- `r = 4` → Read
- `w = 2` → Write
- `x = 1` → Execute

**Example:** `644 (-rw-r--r--)`

Owner can read/write. Group and others can only read.

### Task 4: Modify Permissions
```bash
chmod u+x script.sh
./script.sh

chmod a-w devops.txt
chmod 640 notes.txt

mkdir project
chmod 755 project
ls -l
```
**Observation:** Changed file permissions using `chmod`.

- `444` → Read-only for everyone
- `640` → Owner read/write, group read
- `755` → Owner full access, others read/execute

### Task 5: Test Permissions
```bash
echo "Testing" >> devops.txt
```
**Result:** Permission denied (read-only file).

```bash
chmod u-x script.sh
./script.sh
```
**Result:** Permission denied (no execute permission).

```bash
chmod u+x script.sh
./script.sh
```
**Result:** Hello DevOps

### What I Learned
Practised creating, reading and modifying files. Understood Linux permissions (`rwx`), `chmod`, and how missing permissions cause errors.