dappserver.server_base
=========

This provides a base configuration for a LetheanVPN or dAppServer project that other roles rely on.

Dependencies
------------
This role depends on the following roles:

- geerlingguy.ntp
- geerlingguy.swap

Regionally Aware Role
---------------------
This role is regionally aware and will configure the server for the region it is being deployed to. 
The region is determined by the inventory layout.

The deployment needs the top key of `vpn` in the inventory file as this is used by the GlusterFS configuration.

This role will fail if the inventory is not configured correctly as outline below.

```yaml
vpn:
  children:
    europe: # This is the region
      children:
        london: # This is the region location
          hosts:
            london-01.eu.example.com:
              ansible_user: root
    australia: # This is the region
      children:
        sydney: # This is the region location
          hosts:
            sydney-01.aus.example.com:
              ansible_user: root
    north_america: # This is the region
      children:
        new_york: # This is the region location
          hosts:
            new-york-01.north-america.example.com:
              ansible_user: root
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: dappserver.server_base, x: 42 }

License
-------

EUPL-1.2

