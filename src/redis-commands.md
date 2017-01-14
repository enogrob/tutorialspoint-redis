**Redis - Commands**

Redis commands are used to perform some operations on redis server.

To run commands on redis server you need a redis client. Redis client is available in redis package, which we have installed earlier.

Syntax
Basic syntax of redis client is as follows:
```
$ redis-cli

```

Example
Following example explains how we can start redis client.

To start redis client, open terminal and type the command redis-cli. This will connect to your local server and now you can run any command.
```
$redis-cli
redis 127.0.0.1:6379>
redis 127.0.0.1:6379> PING

PONG
```

In the above example we connect to redis server running on local machine and executes a command PING, that checks whether server is running or not.

Run commands on remote server
To run commands on redis remote server you need to connect to server by same client redis-cli

Syntax
```
$ redis-cli -h host -p port -a password
```

Example
Following example shows how to connect to redis remote server running on host 127.0.0.1, port 6379 and has password mypass.
```
$redis-cli -h 127.0.0.1 -p 6379 -a "mypass"
redis 127.0.0.1:6379>
redis 127.0.0.1:6379> PING

PONG
```
