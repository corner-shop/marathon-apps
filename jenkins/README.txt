 curl -X POST -L  -H 'Content-Type: application/json' -d '@marathon.json'  http://leader.mesos:8080/v2/apps/ 
 curl -X DELETE  -L  -H 'Content-Type: application/json' -d '@marathon.json'  http://leader.mesos:8080/v2/apps/jenkins
 curl -X PUT  -L  -H 'Content-Type: application/json' -d '@marathon.json'  http://leader.mesos:8080/v2/apps/jenkins
