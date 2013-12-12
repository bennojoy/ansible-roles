kerberos_server
========

This role helps in installing Kerberos server on the target host. 
The playbook deploys the kerberos server and creates a new realm as specified in the paramter, it also creates a default admin user which can be used for managing this kerberos server. The default admin name can be specified via "kadmin_user" and password via "kadmin_pass"

Requirements
------------

None

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```
realm_name: EXAMPLE.COM                           # The realm name for the kerneros server
kdc_port: 88                                      # The port in which kdc should listen
master_db_pass: foobar                            # Password for the master kerberos database
kadmin_pass: foobar                               # Password for the kerberos admin
kadmin_user: benz                                 # Username for the kerberos server
```
- Examples

Following is an example which deploys are kerberos server with Realm as BENNO.COM and a admin user "root" and password "foobar"

```
- hosts: all
  roles:
  - {role: kerberos_server, realm_name: "BENNO.COM", kadmin_user: "root" kadmin_pass: "foobar" }

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

