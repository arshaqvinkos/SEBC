
# Get Latest API Version

## Command

```sh
curl -X GET -u arshaqvinkos:cloudera 'http://localhost:7180/api/version'
```

## Results

```sh
v18
```

# Get CM Version

## Command

```sh
curl -u arshaqvinkos:cloudera   'http://localhost:7180/api/v18/cm/version'
```

## Results

```sh 
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
}
```

# List all CM users

## Command

```sh
curl -X GET -u arshaqvinkos:cloudera 'http://localhost:7180/api/v18/users'
```

## Results

```sh
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "arshaqvinkos",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

# Report the database server in use by CM

## Command

```sh
curl -X GET -u arshaqvinkos:cloudera   'http://localhost:7180/api/v18/cm/scmDbInfo'
```

## Results

```sh
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```