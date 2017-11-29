# SnapShot

## Create Directory Precious 

```sh
hdfs dfs -mkdir /user/admin/precious
```

## Put the zip file in directory

```sh
dfs dfs -put /home/hduser/sebc_master.zip /user/admin/precious/
```

## Change owner of precious directory

```sh
hdfs dfs -chown -R admin:admin  /user/admin/*
```
## Create SnapShot

[hdfs@ec2-54-208-253-250 ~]$ hdfs dfsadmin -allowSnapshot /user/admin/precious
Allowing snaphot on /user/admin/precious succeeded

[hdfs@ec2-54-208-253-250 ~]$ hdfs dfs -createSnapshot /user/admin/precious snap_test
Created snapshot /user/admin/precious/.snapshot/snap_test
```

## Delete directory after creating snapshot -Not able to delete


```sh
hdfs dfs -rm -R /user/admin/precious
rm: Failed to move to trash: hdfs://ec2-34-235-121-19.compute-1.amazonaws.com:8020/user/admin/precious: The directory /user/admin/precious cannot be deleted since /user/admin/precious is snapshottable and already has snapshots
```

## Delete zip file

```sh
[hdfs@ec2-54-208-253-250 ~]$ hdfs dfs -rm /user/admin/precious/sebc_master.zip
17/11/28 12:12:03 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ec2-34-235-121-19.compute-1.amazonaws.com:8020/user/admin/precious/sebc_master.zip' to trash at: hdfs://ec2-34-235-121-19.compute-1.amazonaws.com:8020/user/hdfs/.Trash/Current/user/admin/precious/sebc_master.zip
```

## Restore Snapshot

## Listing files in precious directory after restoring

```sh
[hdfs@ec2-54-208-253-250 ~]$ hdfs dfs -ls /user/admin/precious
Found 1 items
-rw-r--r--   3 hdfs admin     474833 2017-11-28 13:00 /user/admin/precious/sebc_master.zip
```
