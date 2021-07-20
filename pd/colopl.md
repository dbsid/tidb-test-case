# colopl test case 
The colopl test case test for hot read scheduler, this case should cause the read bytes and read qps is conflict. 

## test step
1. import prepared data 
the data is real-pd-workload/localtion/GooglePoiSource

```bash
kubectl -n ${K8S_NAMESPACE} run -it br --image=pingcap/br:v5.1.0-nightly --restart=Never bash

```

2. import sql 

relation sql query [query sql](./poisource.sql)

3. bench 

the bench cmd is below: 
```bash
sysbench location.lua  --queries=./poisource.sql --mysql-host=xxx.xx.xxx.xxx --mysql-port=4000 --mysql-user=root  --mysql-db=location --report-interval=1 --events=0 --time=0 --threads=5 --mysql-ignore-errors="all" run 
```
