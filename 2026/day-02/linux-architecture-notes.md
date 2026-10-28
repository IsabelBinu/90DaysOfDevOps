Linux architecture
- Applications
- Shell
- Kernel
- Hardware
Users access applications, Applications access Shells, Shells access Kernel, Kernel access hardware.

Applications: Programs you use, such as Chrome, Python, VS Code, databases, and ls.
Shell: A command interpreter such as Bash or Zsh. It takes commands like ls, cd, or python app.py and asks the operating system to run them.
Linux kernel: The actual core of Linux. It controls CPU time, memory, files, storage, networking, and device drivers.
Hardware: The physical CPU, RAM, disk, keyboard, network card, and so on.

A process is simply a program that is currently alive and being managed by Linux. Its “state” tells you what it is doing or waiting for.
Running - It is either using the CPU now, or ready and waiting for its turn.
Sleeping - It is waiting for something, but can wake up quickly if needed.
Zombie - The program has finished, but its parent has not yet collected its exit result.
Stopped - It has been deliberately paused. It uses no CPU until resumed.

systemd
 systemd is Linux’s main startup and service manager on most modern distributions.
 It starts essential services, starts services in the order, restarts a server if it crashes.

 Most used linux commands - cd, ls, pwd, mdir, cat