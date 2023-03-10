dappserver.server_base
=========

This provides a base configuration for a LetheanVPN or dAppServer project that other roles rely on.

Dependencies
------------
This role depends on the following roles:

- geerlingguy.ntp
- geerlingguy.swap

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: dappserver.server_base, x: 42 }

License
-------

EUPL-1.2

