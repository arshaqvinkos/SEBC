# Pre Install Configuration

## Swappiness Initial Value

```sh
[root@ec2-54-208-253-250 ~]# cat /proc/sys/vm/swappiness 
0
```

## Changing Swappiness to 1

```sh
[root@ec2-54-208-253-250 ~]# sysctl -w vm.swappiness=1
vm.swappiness = 1
```

## Verifying Swappiness Value

```sh
[root@ec2-54-208-253-250 ~]# cat /proc/sys/vm/swappiness 
1
```

## Mount Attributes

```sh
[root@ec2-54-208-253-250 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       50G  4.6G   46G  10% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/xvdb        79G   57M   79G   1% /data/disk0
/dev/xvdc        79G   57M   79G   1% /data/disk1
tmpfs           3.2G     0  3.2G   0% /run/user/1000
```
## Reverse Spacing 

```sh
[root@ec2-54-208-253-250 ~]# lsblk -fm
NAME    FSTYPE LABEL UUID                                 MOUNTPOINT NAME    SIZE OWNER GROUP MODE
xvda                                                                 xvda     50G root  disk  brw-rw----
├─xvda1                                                              ├─xvda1   1M root  disk  brw-rw----
└─xvda2 xfs          de4def96-ff72-4eb9-ad5e-0847257d1866 /          └─xvda2  50G root  disk  brw-rw----
xvdb    ext4         6ca740cc-c88b-4ed1-ba65-82100fcfce71 /data/disk xvdb     80G root  disk  brw-rw----
xvdc    ext4         152ed96e-3f5c-4c8f-b31d-bdbda50a05c1 /data/disk xvdc     80G root  disk  brw-rw----
```

## Chrony

```sh
[root@ec2-54-208-253-250 ~]# systemctl status chrony
Unit chrony.service could not be found.
```

## tuned

```sh
[root@ec2-54-208-253-250 ~]# systemctl status tuned
● tuned.service - Dynamic System Tuning Daemon
   Loaded: loaded (/usr/lib/systemd/system/tuned.service; disabled; vendor preset: enabled)
   Active: inactive (dead)
```

## firewalld

```sh
[root@ec2-54-208-253-250 ~]# systemctl status firewalld
Unit firewalld.service could not be found.
```

## HugePage

```sh
[root@ec2-54-208-253-250 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled 
always madvise [never]

[root@ec2-54-208-253-250 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag 
always madvise [never]
```


## Hosts

```sh
[root@ec2-54-208-253-250 ~]# getent hosts
127.0.0.1       localhost localhost.domain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.domain localhost6 localhost6.localdomain6
172.31.34.12    ec2-54-208-253-250.compute-1.amazonaws.com ec2-54-208-253-250 elephant
172.31.42.0     ec2-52-90-234-250.compute-1.amazonaws.com ec2-52-90-234-250 horse
172.31.33.222   ec2-34-235-121-19.compute-1.amazonaws.com ec2-34-235-121-19 monkey
172.31.37.163   ec2-52-203-1-93.compute-1.amazonaws.com ec2-52-203-1-93 tiger
172.31.46.60    ec2-54-175-91-97.compute-1.amazonaws.com ec2-54-175-91-97 lion

[root@ec2-54-208-253-250 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')
172.31.34.12    ec2-54-208-253-250.compute-1.amazonaws.com ec2-54-208-253-250 elephant
```


## nscd

```sh
[root@ec2-54-208-253-250 ~]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-11-27 13:36:11 CST; 5min ago
  Process: 605 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 609 (nscd)
   CGroup: /system.slice/nscd.service
           └─609 /usr/sbin/nscd

Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 monitoring dire...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 monitoring file...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 monitoring dire...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 monitoring file...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 monitoring dire...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 disabled inotif...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 stat failed for...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com systemd[1]: Started Name Servi...
Nov 27 13:36:11 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 monitored file ...
Nov 27 13:36:30 ec2-54-208-253-250.compute-1.amazonaws.com nscd[609]: 609 checking for mo...
Hint: Some lines were ellipsized, use -l to show in full.
```

## ntpd

```sh
[root@ec2-54-208-253-250 ~]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-11-27 13:42:22 CST; 10s ago
 Main PID: 1680 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─1680 /usr/sbin/ntpd -u ntp:ntp -g

Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com systemd[1]: Started Network Ti...
Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: ntp_io: estimated ...
Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: Listen and drop on...
Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: Listen and drop on...
Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: Listen normally on...
Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: Listen normally on...
Nov 27 13:42:22 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: Listening on routi...
Nov 27 13:42:23 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: 0.0.0.0 c016 06 re...
Nov 27 13:42:23 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: 0.0.0.0 c012 02 fr...
Nov 27 13:42:29 ec2-54-208-253-250.compute-1.amazonaws.com ntpd[1680]: 0.0.0.0 c615 05 cl...
Hint: Some lines were ellipsized, use -l to show in full.
[root@ec2-54-208-253-250 ~]# 
```


