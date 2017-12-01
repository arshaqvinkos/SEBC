
# Repo List

```sh
cloudera-manager.repo  redhat-rhui-client-config.repo  rhui-load-balancers.conf
redhat.repo            redhat-rhui.repo
```


# Connect Cloudera Manager Server to its database

## Command

```sh
/usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-29-46.ec2.internal -u root -p  scm scm scm_password
Enter database password: 
```

## OUTPUT


```sh
JAVA_HOME=/usr/java/jdk1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!

```