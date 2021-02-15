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

### What is SSH?

It is called Securtiy Shell (SSH)

### Why I got an "permission denied" error when ssh into a linux server?

First you need to check the status of services. 
```
sudo service ssh status
sudo service ssh restart
```
Check if you have wrong credentials, then check which port is being used for SSH 
```
grep Port /etc/ssh/sshd_config
```
Check if the above port is closed
```
sudo lsof -i -n -P | grep LISTEN
```
Check if SSH is installed on your server.
```
sudo service ssh restart
```




