# redis_bench

> project import youzan, made some adjustments, just make it easier to use.

redis benchmark tool by golang

### Usage

```
> go run bench.go -h

help:
  -c int
    	number of clients (default 100)
  -ip string
    	redis server ip (default "127.0.0.1")
  -maxExpire int
    	max expire seconds to be allowed with setex (default 60)
  -minExpire int
    	min expire seconds to be allowed with setex (default 10)
  -n int
    	request number (default 100000)
  -namespace string
    	the prefix namespace (default "default")
  -pkn int
    	primary key count for hash,list,set,zset (default 100)
  -port int
    	redis server port (default 6379)
  -r int
    	benchmark round number (default 1)
  -t string
    	only run the comma separated list of tests (default "set,get,randget,del,lpush,lrange,lpop,hset,hget,hdel,zadd,zrange,zrevrange,zdel")
  -table string
    	the table to write (default "test")
  -vsize int
    	kv value size (default 100)
```

### How to run

```
> go build bench.go
> ./bench

set: 1.970729428s 19.707 micros/op, 50742.63op/s
get: 1.642698759s 16.427 micros/op, 60875.43op/s
randget: 1.702335425s 17.023 micros/op, 58742.83op/s
del: 1.53211802s 15.321 micros/op, 65269.12op/s
rpush: 1.925137846s 19.251 micros/op, 51944.33op/s
lrange10: 2.055337954s 20.553 micros/op, 48653.80op/s
lrange50: 318.9238ms 3.189 micros/op, 313554.52op/s
lrange100: 387.524722ms 3.875 micros/op, 258048.05op/s
lpop: 1.650401604s 16.504 micros/op, 60591.31op/s
hset: 1.693249018s 16.932 micros/op, 59058.06op/s
hrandget: 1.565766041s 15.658 micros/op, 63866.50op/s
hget: 1.563251735s 15.633 micros/op, 63969.22op/s
hdel: 1.570401131s 15.704 micros/op, 63678.00op/s
zadd: 1.845827673s 18.458 micros/op, 54176.24op/s
zrange: 534.219896ms 5.342 micros/op, 187188.84op/s
zrangebyscore: 976.370655ms 9.764 micros/op, 102420.12op/s
zrevrange: 533.78739ms 5.338 micros/op, 187340.51op/s
zrevrangebyscore: 356.652401ms 3.567 micros/op, 280385.05op/s
zrem: 1.507580092s 15.076 micros/op, 66331.47op/s
```

