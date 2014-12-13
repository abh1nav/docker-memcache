# DevDB Memcache

Memcache v1.4.14 in a docker container - single node for development.

## Quickstart

```
docker pull devdb/memcache:latest
docker run -d --name memcache -p 11211:11211 devdb/memcache:latest
```

Once the container is running, you can test it using telnet:

```
telnet localhost 11211
```

And then,

```
stats
```

This should print out a bunch of stats about memcache. Type `quit` to close the telnet session.

#### Memory Allocation

By default, the container starts memcache with a maximum 64MB memory usage cap (memcache default). If you want to specify max memory usage, you can specify the `MAX_MEM` environment variable. For example, to run it with a max of 128MB, use:

```
docker pull devdb/memcache:latest
docker run -d --name memcache -p 11211:11211 -e MAX_MEM=128 devdb/memcache:latest
```