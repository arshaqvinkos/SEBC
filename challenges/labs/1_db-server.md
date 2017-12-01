# DataBase HostName

## Command

```sh
MariaDB [(none)]> select @@hostname;
```

## Output

```sh
+------------------------------+
| @@hostname                   |
+------------------------------+
| ip-172-31-29-46.ec2.internal |
+------------------------------+
1 row in set (0.00 sec)
```


# DataBase Version

## Command

```sh
mysql -V
```
## Ouptput

```sh
mysql  Ver 15.1 Distrib 10.1.29-MariaDB, for Linux (x86_64) using readline 5.1
```

# List Databases

## Command

```sh
MariaDB [(none)]> SHOW DATABASES;
```

## Output

```sh
+--------------------+
| Database           |
+--------------------+
| hive               |
| hue                |
| information_schema |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
8 rows in set (0.00 sec)
```