# Redis Cheat Sheet

[Data Type Intro](https://redis.io/topics/data-types-intro)

## Redis Keys
- any binary sequence <512MB
- long keys are discouraged. hashing it is encouraged
- use ':', '.' or '-' to seperate fields

## Redis Strings
`set mykey newval nx (only set if key not exist)`  
`set mykey newval xx (only set if key exist)`  
`set counter 100`  
`incr counter` // redis parse value as int and do atomic increment  
`INCRBY`, `DECR` and `DECRBY`  
```
> mset a 10 b 20 c 30
OK
> mget a b c
1) "10"
2) "20"
3) "30"
```
```
> set key some-value
OK
> expire key 5 (in sec. pexpire:in milliseconds)
(integer) 1
> get key (immediately)
"some-value"
> get key (after some time)
(nil)
> set key 100 ex 10
OK
> ttl key
(integer) 9
```

## Redis Lists
- implemented via Linked Lists
```
> rpush mylist A (can push multiple)
(integer) 1
> rpush mylist B
(integer) 2
> lpush mylist first
(integer) 3
> lrange mylist 0 -1 (-1 is the last element, -2 is the 2nd last element of the list, and so forth)
1) "first"
2) "A"
3) "B"
```
- `lpop`, `rpop`

