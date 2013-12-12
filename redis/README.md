kerberos_client
========

This role helps to deploy a Redis master or replication server on target host. This roles sets several default values for redis configuratiaon which can be overrriden by the user.


Requirements
------------

none

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```
redis_port: 6379                           # Port for redis server
syslog_enabled: "yes"                      # enable_syslog
databases: 16                              # Set number of databases
database_save_times:                       # Save the DB on disk (seconds changes)
  - [900, 1]
  - [300, 10]
  - [60, 10000]
dbfilename: dump.rdb                       # Filename for the db
db_dir: /var/lib/redis                     # DB directory
redis_role: master                         # The role for this redis deployment (master/slave)
requirepass: false                         # If password is required for querying
redis_pass: None                           # Password if require_pass is enabled
max_clients: 128                           # max clients
max_memory: 512mb                          # max memory to be used
maxmemory_policy: volatile-lru             # memory Policy
appendfsync: everysec                      # How often to sync fs
#If role is slave set these values too
master_ip: 1.1.1.1                         # The master's ip
master_port: 6379                          # master port
master_auth: None                          # master auth
```

- Examples:

The Following example sets up a master redis server.
```
- hosts: all
  sudo: true
  roles:
  - {role: redis, redis_port: 11244}

```
The Following example sets up a slave redis server.

```

- hosts: all
  sudo: true
  roles:
  - {role: redis, redis_role: 'slave', master_ip: '192.168.2.10', master_auth: 'foobar'}


```



Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Ansible Staff


