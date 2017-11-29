
## Create kerberos user

```sh
[root@ec2-54-208-253-250 ~]# kadmin.local
Authenticating as principal root/admin@VINKOS.COM with password.
kadmin.local:  addprinc arshaqvinkos@VINKOS.COM
WARNING: no policy specified for arshaqvinkos@VINKOS.COM; defaulting to no policy
Enter password for principal "arshaqvinkos@VINKOS.COM": 
Re-enter password for principal "arshaqvinkos@VINKOS.COM": 
Principal "arshaqvinkos@VINKOS.COM" created.
```


## kinit command 

```sh
kinit arshaqvinkos@VINKOS.COM
Password for arshaqvinkos@VINKOS.COM: 
```

## klist command

```sh
[ec2-user@ec2-54-175-91-97 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1000
Default principal: arshaqvinkos@VINKOS.COM

Valid starting       Expires              Service principal
11/29/2017 11:12:22  11/30/2017 11:12:22  krbtgt/VINKOS.COM@VINKOS.COM
	renew until 12/06/2017 11:12:22
```