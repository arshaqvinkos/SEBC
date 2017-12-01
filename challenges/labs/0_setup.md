# Provider

```sh
Provider - AWS
```

# IP Address and DNS

```sh

ec2-54-146-229-183.compute-1.amazonaws.com     54.146.229.183
ec2-52-87-253-195.compute-1.amazonaws.com      52.87.253.195
ec2-34-234-64-159.compute-1.amazonaws.com      34.234.64.159
ec2-204-236-220-196.compute-1.amazonaws.com    204.236.220.196
ec2-54-224-93-122.compute-1.amazonaws.com      54.224.93.122
```

# Linux Release

```sh
Red Hat Enterprise Linux Server release 7.4 (Maipo)
```

# File System Capacity

```sh
[[root@ip-172-31-29-62 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       50G  1.3G   49G   3% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
tmpfs           3.2G     0  3.2G   0% /run/user/1000
tmpfs           3.2G     0  3.2G   0% /run/user/0
/dev/xvdb        79G   57M   79G   1% /data/disk0
/dev/xvdc        79G   57M   79G   1% /data/disk1
[root@ip-172-31-29-62 ~]# 

```


# Repolist enabled

```sh
yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                           status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastructure 2.0 C      8
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux Server 7 ( 17,521
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux Server 7 R    228
repolist: 17,757

```

# Add User and Groups

```sh
[root@ip-172-31-29-62 ~]# groupadd comets
[root@ip-172-31-29-62 ~]# groupadd planets
[root@ip-172-31-29-62 ~]# adduser -u 2900 -m -g comets haley
[root@ip-172-31-29-62 ~]# adduser -u 2800 -m -g planets saturn
```

# List /etc/passwd

```sh
[root@ip-172-31-29-62 ~]# grep -e haley -e saturn /etc/passwd
haley:x:2900:1002::/home/haley:/bin/bash
saturn:x:2800:1003::/home/saturn:/bin/bash
```

# List /etc/group

```sh
[root@ip-172-31-29-62 ~]# grep -e planets -e comets /etc/group
comets:x:1002:
planets:x:1003:
```