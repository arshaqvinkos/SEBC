
## Ubertask Optimization

```sh
Ubertask optimization allows to run sufficiently small jobs sequentially within a single JVM."Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

Usually seperate containers are created for mapper and reducer tasks.But if we have small dataset,ubertask configuration will allow mapper and reducers to run in the same process as teh ApplicationMaster thus reducing cost and time.

```

## Where in CM is the Kerberos Security Realm value displayed?

```sh
In Cloudera Manager 
Go to Administration > Settings

Choose Category kerberos 

Kerberos realm is under property "Kerberos Security Realm (default_realm)"

```

## Which CDH service(s) host a property for enabling Kerberos authentication?

```sh
In general for services, kerberos is enabled by 

1.Initial kerberos configuration in hosts.
2. Using Cloudera Manager Administration > settings > Enable kerberos configurations.

Once the services are kerberized, there are some additional kerberos authentication properties provided by CDH Services

1- HDFS Service > Configuration > Enable Kerberos Authentication for HTTP Web-Consoles

2.Yarn Service > Configuration > Enable Kerberos Authentication for HTTP Web-Consoles

3. Zookeeper Service > Configuration > Enable Kerberos Authentication
```

## How do you upgrade the CM agents?

```sh
The first step is to update CM server. Once the CM Server is updated and restarted,log in to the Cloudera Manager Admin Console. It can take several minutes for Cloudera Manager Server to start, and the console is unavailable until the server startup is complete.
The Upgrade Wizard displays. Follow the steps below to upgrade CM agents through CM.


1. Select Yes, I would like to upgrade the Cloudera Manager Agent packages now and click Continue.
2. Select the release of the Cloudera Manager Agent to install. 
3. Click Continue. The JDK Installation Options page displays.(If you want Cloudera Manager to install JDK 1.7 on all cluster hosts,select Install Oracle Java SE Development Kit (JDK))
4. Click Continue.
5. Specify credentials and initiate Agent installation:
6. Select root or enter the username for an account that has password-less sudo permission.
7. Select an authentication method:
      If you choose password authentication, enter and confirm the password.
      If you choose public-key authentication, provide a passphrase and path to the required key files.
      You can specify an alternate SSH port. The default value is 22.
      You can specify the maximum number of host installations to run at once. The default value is 10.
8. Click Continue.
9. The Cloudera Manager Agent packages and, if selected, the JDK are installed.
10. Click Continue.
11. The Host Inspector runs to inspect your managed hosts for correct versions and configurations. If problems occur, you can make changes and then rerun the inspector.
12. When you are satisfied with the inspection results, click Continue.
```


## Give the tsquery statement used to chart Hue's CPU utilization?

```sh
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
```

## Name all the roles that make up the Hive service

```sh
Gateway5
Hive Metastore Server2
HiveServer2
```

## What steps must be completed before integrating Cloudera Manager with Kerberos?

```sh
Pre-requisite : You have a hadoop cluster managed by Cloudera Manager.

Steps:
1. Choose a kerberos server and install the required packages for kerberos server
2. In all the nodes, install kerberos client packages
3. In the server, choose a realm name and edit the config files with the required parameters. Config files are 
	- /var/kerberos/krb5kdc/kdc.conf
	- /etc/krb5.conf
	- /var/kerberos/krb5kdc/kadm5.acl 
4. In server, create the database using kdb5_util utility.
5. In all clients, use the same configurations as server in /etc/krb5.conf file.
6. In server, add cloudera-scm principal.
7. Start kerberos services.
8. Go to Cloudera Manager UI and continue kerberos configuration

```

