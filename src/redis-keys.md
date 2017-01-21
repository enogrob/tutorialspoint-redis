**Redis - Keys**

Redis keys commands are used for managing keys in redis. Syntax for using redis keys commands is shown below:

Syntax
```
redis 127.0.0.1:6379> COMMAND KEY_NAME
```

Example
```sql
redis 127.0.0.1:6379> SET tutorialspoint redis
OK
redis 127.0.0.1:6379> DEL tutorialspoint
(integer) 1
```

In the above example `DEL` is the command, while `tutorialspoint` is the key. If the key is deleted, then output of the command will be `(integer) 1`, otherwise it will be `(integer) 0`.

**Redis keys commands**

Below given table shows some basic commands related to keys:

`DEL key` This command deletes the key, if exists
```sql
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> DEL tutorialspoint
(integer) 1
```

`DUMP key` This command returns a serialized version of the value stored at the specified key.
```sql
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> DUMP tutorialspoint
"\x00\x05redis\x06\x00S\xbd\xc1q\x17z\x81\xb2"
```

`EXISTS key` This command checks whether the key exists or not.
```sql
127.0.0.1:6379> EXISTS tutorialspoint-new-key
(integer) 0
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> EXISTS tutorialspoint
(integer) 1
```

`EXPIRE key seconds` Expires the key after the specified time.
```sql
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> EXPIRE tutorialspoint 60
(integer) 1
127.0.0.1:6379> GET tutorialspoint
"redis"
127.0.0.1:6379> GET tutorialspoint
(nil)
```

`EXPIREAT key timestamp` Expires the key after the specified time. Here time is in Unix timestamp format.
```sql
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> EXPIREAT tutorialspoint 1293840000
(integer) 1
EXISTS tutorialspoint
(integer) 0
```

`PEXPIRE key milliseconds` Set the expiry of key in milliseconds.
```sql
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> PEXPIRE tutorialspoint 5000
(integer) 1
```

`PEXPIREAT key milliseconds-timestamp` Set the expiry of key in unix timestamp specified as milliseconds.
```sql
127.0.0.1:6379> SET tutorialspoint redis
OK
127.0.0.1:6379> PEXPIREAT tutorialspoint 1555555555005
(integer) 1
```

`KEYS pattern` Find all keys matching the specified pattern.
```sql
127.0.0.1:6379> SET tutorial1 redis
OK
127.0.0.1:6379> SET tutorial2 mysql
OK
127.0.0.1:6379> SET tutorial3 mongodb
OK
127.0.0.1:6379> KEYS tutorial*
1) "tutorial3"
2) "tutorial1"
3) "tutorial2"
127.0.0.1:6379> KEYS *
1) "tutorial3"
2) "tutorial1"
3) "tutorial2"
```

`MOVE key db` Move a key to another database. In redis by default 0th database is selected, so now we are moving the generated key in second database.
```sql
127.0.0.1:6379> SET tutorial1 redis
OK
127.0.0.1:6379> MOVE tutorial1 1
1) (integer) 1
```

`PERSIST key` Remove the expiration from the key.

`PTTL key` Get the remaining time in keys expiry in milliseconds.

`TTL key` Get the remaining time in keys expiry.

`RANDOMKEY` Return a random key from redis.

`RENAME key newkey` Change the key name.

`RENAMENX key newkey` Rename key, if new key doesn't exist.

`TYPE key` Return the data type of value stored in key.
