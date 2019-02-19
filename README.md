[![CircleCI](https://circleci.com/gh/RedisLabsModules/rebloom.svg?style=svg)](https://circleci.com/gh/RedisLabsModules/rebloom)
[![GitHub issues](https://img.shields.io/github/release/RedisLabsModules/rebloom.svg)](https://github.com/RedisLabsModules/rebloom/releases/latest)
[![DockerHub](https://dockerbuildbadges.quelltext.eu/status.svg?organization=redislabs&repository=rebloom)](https://hub.docker.com/r/redislabs/rebloom/builds/) 

# ReBloom - Bloom Filter Module for Redis

This module provides two probabalistic data structures as Redis data types:
**Bloom Filters** and **Cuckoo Filters**. These two structures are similar in
their purpose but have different performance and functionality characteristics

## Quick Start Guide
1. [Launch ReBloom with Docker](#launch-rebloom-with-docker)
1. [Use Rebloom with redis-cli](#use-rebloom-with-redis-cli)

Note: You can also [build and load the module](#building-and-loading-rebloom) yourself.

You can find command references in [Bloom_Commands.md](docs/Bloom_Commands.md) and [Cuckoo_Commands.md](docs/Cuckoo_Commands.md)


### 1. Launch ReBloom with Docker
```
docker run -p 6379:6379 --name redis-rebloom redislabs/rebloom:latest
```

### 2. Use ReBloom with `redis-cli`
```
docker exec -it redis-rebloom bash

# redis-cli
# 127.0.0.1:6379> 
```

Start a new bloom filter by adding a new item
```
# 127.0.0.1:6379> BF.ADD newFilter foo
(integer) 1
``` 

 Checking if an item exists in the filter
```
# 127.0.0.1:6379> BF.EXISTS newFilter foo
(integer) 1
```


## Building and Loading ReBloom

In order to use this module, build it using `make` and load it into Redis.

### Loading

**Invoking redis with the module loaded**

```
$ redis-server --loadmodule /path/to/rebloom.so
```

You can find a command reference in [docs/Bloom_Commands.md](docs/Bloom_Commands.md)

