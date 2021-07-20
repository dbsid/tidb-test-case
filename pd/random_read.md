# random read test case 
The test case for random hot read
## step
1. prepare

the prepare cmd is below: 
```
sysbench --config-file=config select_random_points --tables=1 --table-size=50000000 --rand-type=uniform --mysql-host=xxx.xxx.xx  --mysql-port=4000 --mysql-user=root  --mysql-db=location --report-interval=1 --events=0 --time=0 --threads=100 prepare
```

2. run 

the run cmd is below: 
```
sysbench --config-file=config select_random_points --tables=1 --table-size=50000000 --rand-type=uniform --mysql-host=xxx.xxx.xx  --mysql-port=4000 --mysql-user=root  --mysql-db=location --report-interval=1 --events=0 --time=0 --threads=100 run 
```