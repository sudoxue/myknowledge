### How do I access my C: drive?
Mount points for hard drives on the local machine are automatically created and provide easy access to the Windows filesystem. 
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
You need to change to mnt\c\
```bash
cd /mnt/c

```
![result](/Windows/images/sf.png)

