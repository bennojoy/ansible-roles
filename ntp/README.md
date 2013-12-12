ntp
========

This Role enables users to Install and configure ntp on thier hosts

Requirements
------------

None

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```
driftfile: /var/lib/ntp/drifta                                      # The driftfile
server: [0.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]              # The server to sync time with
restrict:                                                           # List of restrict's for ntp daemon
  - "restrict -4 default kod notrap nomodify nopeer noquery"
  - "restrict -6 default kod notrap nomodify nopeer noquery"
  - "restrict 127.0.0.1"

crypto: no                                                          #Use cryptography
includefile: no                                                     #To use includefiles or not
keys: no                                                            #The keys to be used incase crypto is enabled
trustedkey: no
requestkey: no
controlkey: no
statistics: no
broadcast: no                                                       #Broadcast the time in network
broadcastclient: no                                                 #Function as a broadcast client
multicastclient: no                                                 # Function as multicast client
```

- Examples

1) Install ntp set the default settings.

```
- hosts: all
  roles:
    - role: ntp
```

2) Install ntp and send down some custom servers

```

- hosts: all
  roles:
    - role: ntp
      server: [2.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]

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

