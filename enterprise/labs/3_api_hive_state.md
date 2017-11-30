# Stop Service
 
## Command	

```sh
  curl -X POST -u arshaqvinkos:cloudera 'http://localhost:7180/api/v17/clusters/Cluster_SEBC/services/hive/commands/stop'
```

## Output

```sh
{
  "id" : 1785,
  "name" : "Stop",
  "startTime" : "2017-11-30T17:44:55.032Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```

 # Start Service

## Command	

```sh
  curl -X POST -u arshaqvinkos:cloudera 'http://localhost:7180/api/v17/clusters/Cluster_SEBC/services/hive/commands/start'
```
## Output

```sh
{
  "id" : 1794,
  "name" : "Start",
  "startTime" : "2017-11-30T17:47:52.152Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```


# Check Status

## Command	

```sh
  curl -u arshaqvinkos:cloudera 'http://localhost:7180/api/v17/clusters/Cluster_SEBC/services/hive'
```

## Output

```sh
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ec2-54-208-253-250.compute-1.amazonaws.com:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ec2-54-208-253-250.compute-1.amazonaws.com:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```