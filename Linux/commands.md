### What does 'tee' command do?
the most basic usage of the tee command is to display the standard output(stout)of a program and write it in a file

```bash
$df -h | tee disk_usage.txt  
Filesystem      Size  Used Avail Use% Mounted on
rootfs          476G  178G  299G  38% /
none            476G  178G  299G  38% /dev
none            476G  178G  299G  38% /run
none            476G  178G  299G  38% /run/lock
none            476G  178G  299G  38% /run/shm
none            476G  178G  299G  38% /run/user
tmpfs           476G  178G  299G  38% /sys/fs/cgroup
C:\             476G  178G  299G  38% /mnt/c
```

### How to make cut/copy/paste in Ubuntu terminal
In most applications Cut, Copy and Paste are Ctrl + X, Ctrl + C and Ctrl+V respectively.
In the Terminal, Ctrl+C is the cancel command. Use these in the terminal instead:
To cut Ctrl + Shift + X.
To copy Ctrl + Shift + C.
To paste Ctrl + Shift + V.