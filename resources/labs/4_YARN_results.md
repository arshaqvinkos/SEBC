
# Fast Run - Memory 512 1024

```sh
[hdfs@ec2-54-208-253-250 ~]$ /home/hduser/YARNtest.sh 
Testing loop started on Tue Nov 28 15:07:54 CST 2017
 Mapper Containers=8,Reducer Containers =1, Container Memory =512, MAP_MB=409,RED_MB=409 

-- Teragen
real	1m20.255s
user	0m6.621s
sys	0m0.327s


-- Terasort

real	3m44.608s
user	0m8.705s
sys	0m0.398s

Deleted /results/tg-10GB-8-1-512
Deleted /results/ts-10GB-8-1-512


Mapper Containers=8,Reducer Containers =1, Container Memory =1024, MAP_MB=819,RED_MB=819 

real	1m22.552s
user	0m6.641s
sys	0m0.333s

real	3m40.010s
user	0m8.933s
sys	0m0.405s
Deleted /results/tg-10GB-8-1-1024
Deleted /results/ts-10GB-8-1-1024
Testing loop ended on Tue Nov 28 15:18:10 CST 2017
```

## Slow Run - Memory 8192 10240

```sh
[hdfs@ec2-54-208-253-250 ~]$ /home/hduser/YARNtest.sh 
Testing loop started on Tue Nov 28 15:58:55 CST 2017
Mapper Containers=8,Reducer Containers =1, Container Memory =8192, MAP_MB=6553,RED_MB=6553 

real	1m40.307s
user	0m6.807s
sys	0m0.337s

real	7m10.254s
user	0m8.311s
sys	0m0.374s
Deleted /results/tg-10GB-8-1-8192
Deleted /results/ts-10GB-8-1-8192
Mapper Containers=8,Reducer Containers =1, Container Memory =10240, MAP_MB=8192,RED_MB=8192 

real	1m41.613s
user	0m7.230s
sys	0m0.339s

real	17m28.680s
user	0m9.683s
sys	0m0.522s
Deleted /results/tg-10GB-8-1-10240
Deleted /results/ts-10GB-8-1-10240
```