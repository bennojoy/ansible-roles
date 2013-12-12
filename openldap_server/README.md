openldap_server
========

This roles installs openldap server on the Target. It has the option to enable/disable ssl
by setting it in defaults or overriding it.

Requirements
------------

None

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

domain_name: example.com               # The domain prefix for ldap
rootpw: passme                         # This is the password for admin for openldap

enable_ssl: true                       # To enable/disable ssl for the ldap
country: US                            # The self signed ssl certificate parameters
state: oregon
location: portland
organization: IT


Dependencies
------------

None

License
-------


Author Information
------------------

Ansible Staff

