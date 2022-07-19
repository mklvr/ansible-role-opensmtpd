Role Name
=========

Install and configure OpenSMTPD from backports on Debian

Requirements
------------

Nothing special.

Role Variables
--------------

opensmtpd_ssl_cert: "/etc/ssl/certs/{{ ansible_fqdn }}.crt"
opensmtpd_ssl_key: "{{ openssl_private_key['filename'] }}"
alt_domains:
  - domain1.com
  - domain2.com

Dependencies
------------

The variable `openssl_private_key['filename']` won't be defined unless you run ansible-role-acme-cert. You can, of course, just specify it to your own desired cert/key.

Example Playbook
----------------

    - hosts: servers
      vars:
        alt_domains:
          - domain1.com
          - domain2.com
      roles:
        - ansible-role-acme-cert # See above
        - ansible-role-opensmtpd

License
-------

MIT

Author Information
------------------

Mike Oliver (mike@mklvr.io)
