
# Verifying Privileges

```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ec2-52-90-234-250.compute-1.amazonaws.com@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ec2-52-90-234-250.compute-1.amazonaws.com@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHow tables;
INFO  : Compiling command(queryId=hive_20171129184747_6ea33285-5742-41ab-a5ea-6d9a63ec3629): SHow tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129184747_6ea33285-5742-41ab-a5ea-6d9a63ec3629); Time taken: 0.697 seconds
INFO  : Executing command(queryId=hive_20171129184747_6ea33285-5742-41ab-a5ea-6d9a63ec3629): SHow tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129184747_6ea33285-5742-41ab-a5ea-6d9a63ec3629); Time taken: 0.217 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.228 seconds)
0: jdbc:hive2://localhost:10000/default> 

```


# Verifying privileges with full autherization

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP hadoop;
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129185757_6e4fd0dd-5491-4b70-b310-c8527cf75b80): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129185757_6e4fd0dd-5491-4b70-b310-c8527cf75b80); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171129185757_6e4fd0dd-5491-4b70-b310-c8527cf75b80): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129185757_6e4fd0dd-5491-4b70-b310-c8527cf75b80); Time taken: 0.154 seconds
INFO  : OK
+-------------------------------------+--+
|              tab_name               |
+-------------------------------------+--+
| demographic_statistics_by_zip_code  |
| sample_04                           |
| sample_05                           |
| sample_06                           |
| sample_07                           |
+-------------------------------------+--+

5 row selected (0.287 seconds)

```

# Running as George

```
[ec2-user@ec2-52-90-234-250 ~]$ kinit george
Password for george@VINKOS.COM: 
[ec2-user@ec2-52-90-234-250 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ec2-52-90-234-250.compute-1.amazonaws.com@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ec2-52-90-234-250.compute-1.amazonaws.com@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129191515_17b09834-212c-44fc-ae3a-12624f715b90): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129191515_17b09834-212c-44fc-ae3a-12624f715b90); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171129191515_17b09834-212c-44fc-ae3a-12624f715b90): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129191515_17b09834-212c-44fc-ae3a-12624f715b90); Time taken: 0.114 seconds
INFO  : OK
+-------------------------------------+--+
|              tab_name               |
+-------------------------------------+--+
| demographic_statistics_by_zip_code  |
| sample_04                           |
| sample_05                           |
| sample_06                           |
| sample_07                           |
+-------------------------------------+--+
5 rows selected (0.25 seconds)
0: jdbc:hive2://localhost:10000/default> 
```

# Running as ferdinand

```
[ec2-user@ec2-52-90-234-250 ~]$ kinit ferdinand
Password for ferdinand@VINKOS.COM: 
[ec2-user@ec2-52-90-234-250 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1000
Default principal: ferdinand@VINKOS.COM

Valid starting       Expires              Service principal
11/29/2017 13:17:29  11/30/2017 13:17:29  krbtgt/VINKOS.COM@VINKOS.COM
	renew until 12/06/2017 13:17:29
[ec2-user@ec2-52-90-234-250 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ec2-52-90-234-250.compute-1.amazonaws.com@VINKOS.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ec2-52-90-234-250.compute-1.amazonaws.com@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129191717_065afd94-a351-4a18-bf05-0f32452a0cb6): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129191717_065afd94-a351-4a18-bf05-0f32452a0cb6); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171129191717_065afd94-a351-4a18-bf05-0f32452a0cb6): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129191717_065afd94-a351-4a18-bf05-0f32452a0cb6); Time taken: 0.107 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.242 seconds)
0: jdbc:hive2://localhost:10000/default> 

```