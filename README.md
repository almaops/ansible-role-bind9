# almaops.bind9
This ansible role installs and condifures Bind9 DNS server.  

# Requirements
Tested only on Ubuntu 20.04.  

# Role variables
Look into [defaults](./defaults/main.yml)

# Example playbook
```
- hosts: dns_servers
  become: true
  roles:
    - role: almaops.bind9
      bind9_bind_addr_ipv4:
        - '127.0.0.1'
        - '192.168.0.1'
      bind9_conf_options_allow_recursion:
        - "any"
      bind9_conf_options_recursion: "yes"
      # Use Cloudflare as forward resolver
      bind9_conf_options_forwarders:
        - '1.1.1.1'
        - '1.0.0.1'
```

# License
[MIT License](./LICENSE)

# Author Information
Valentin Gostev
