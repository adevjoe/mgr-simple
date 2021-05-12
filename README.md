1. start mysql    
```
docker-compose up -d
```

2. exec one of those containers
```
docker exec -it container_id bash
```

3. login mysqlshell
```
mysqlsh --uri root:password@db-1:3306
```

4. create cluster
```
dba.createCluster('Cluster')
```

5. add instance
```
dba.getCluster().addInstance('root:123@db-2:3306', {'recoveryMethod': 'clone'})
dba.getCluster().addInstance('root:123@db-3:3306', {'recoveryMethod': 'clone'})
```

6. check instance state
```
dba.getCluster().status()
```
