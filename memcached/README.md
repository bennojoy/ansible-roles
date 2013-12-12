memcached
========

This role helps to install a memcached server on target host.

Requirements
------------

None

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```
port: 11211                               # The port in which memcached server should be listening
max_conn: 1024                            # The number of max concurrent connections it shoud accept
cache_size: 64                            # The cache size
fs_file_max: 756024                       # The kernel paramter for max number of file handles
```
- Example

The following play setup's memcached with a diffrent port number and available memory 

```

- hosts: all
  sudo: true
  roles:
  - {role: memcached, port: 11244, cache_size: 512 }

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
