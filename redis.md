#### Launch Redis on computer start
    ln -sfv /usr/local/opt/redis/*.plist ~/Library/LaunchAgents

#### Start Redis server via “launchctl” for launched daemons
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.redis.plist

#### redis commands
     brew services stop redis
     brew services start redis


## Redis

Redis is a TCP server using client-server model

=> Loopback interface to cut on RTT
=> Pipelining by sending multiple commands to the server without waiting for response at all and then reading all responses in single go.
    Server queues the request, so if you need to send a lot of commands then send them in batches, read the replies then send another batch

    Why pipelining helps?
      It not only reduces latency cost in RTT but also improves on total operations u can perform in a single second.
      Major overhead is in Socket I/O as it involves calling read() and write() syscall i.e., goinf from user land to kernel land. This context
      switch is a huge penalty. When pipelining, many commands are read with single read() and many writes with single write() system call.

=> Pub/ Sub =========
  Publisher publish to a channel irrespective to subscribers -> PUBLISH channel message
  Subscriber can subscribe to multiple channels -> SUBSCRIBE channels
  Pub/sub are on different db numbers

  Pattern-matching:
    PSUBSCRIBE
    PUNSUBSCRIBE

=> Expire ========
  set a timeout on key
  Keys are expired in following ways ----
    Passive : A key is passively expired when some client tries to access a key and key is found to be timed out.
    Active : Periodically redis tests a few keys at random among keys within an expired set.

  Application ----
    If the user will be idle more than 60 seconds, the key will be deleted and only subsequent page views that have less than 
    60 seconds of difference will be recorded.

  Handling expiry in replica nodes and AOF file -------
  In order to obtain a correct behavior without sacrificing consistency, when a key expires, a DEL operation is synthesized in both the 
  AOF file and gains all the attached replicas nodes. This way the expiration process is centralized in the master instance, and there 
  is no chance of consistency errors.


=> Transaction ============
  Commands in transaction are serialized and executed sequentially. Commands are executed as single isolated operation.
  Redis transaction is atomic, either all are processed or none.

  EXEC - To execute all commands that are part of Transaction block.
  DISCARD - It flush the transaction queue and exit the transaction.

  Errors :
    before EXEC is called
    after EXEC is called

  Rollback not supported :
    Redis will execute a transaction if some command fails during transaction as rails commands fail because of programming errors like wrong
    syntax or keys holding the wrong data type.

=>  WATCH ------
    To provide check and set behaviour to transactions. It makes EXEC conditional.
    We ask Redis to peform transactions if none of the watched keys are modified.
    When EXEC is called, all keys are UNWATCHed

    UNWATCH command to flush all the watched keys.

    Application -  implement ZPOP

=> LRU Cache  -----------
  maxmemory directive, LRU eviction policies are used after cache memory exceeeds it
  INFO - to monitor cache misses or hits
  evict keys using LRU, randomly or TTL among all keys or volatile keys(expired keys)

  LFU - Least frequently used mode
    With LRU, an item that was recently accessed but actually never requested will never get evicted.
    Used probabilistic counter called Morris counter to estimate the object access frequency, combined with a decay period


    
