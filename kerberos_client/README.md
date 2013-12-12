kerberos_client
========

This role would configure the host that it is run against as a kerberos client.

Requirements
------------

This role requires that you have a working kerberos server and you know the realm name and the client has access to the 
kerberos server port
 
Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```

realm_name: EXAMPLE.COM                   # The name of the kerberos Realm

kdc_hostname: kerberos                    # The hostname running the kerberos server

admin_hostname: kerberos                  # The hostname of the server runinng the kerneros administration server

dns_lookup_realm: "false"                 # If dns should be looked up for the realm

dns_lookup_kdc: "false"                   # IF dns should be looked up for kdc

ticket_lifetime: "24h"                    # The lifetime for the ticket issued

renew_lifetime: "7d"                      # when to renew the lifetime

forwardable: "true"                       # Obtain a forwardable ticket.

```

- Example

Following is an example which deploys are kerberos client  with Realm as BENNO.COM and a admin user "root" and password "foobar"

```
- hosts: all
  roles:
  - {role: kerberos_client, realm_name: "BENNO.COM", kadmin_user: "root" kadmin_pass: "foobar", kdc_hostname: "foobar" }

```

Dependencies
------------

None

License
-------


Author Information
------------------

Ansible Staff

