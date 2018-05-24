# Network VRF Configuration

Ansible role that defines the vrfs for networking devices. 

The configuration of the role is done so that it shouldn't be necessary to modify the role for any configuration.
All settings can be configured by changing role parameters or by declaring new config as variable.

Please report any issues or send PR.


Details from modules used: 
Cisco NX-OS creates the default VRF by itself. Therefore, you’re not allowed to use default as vrf name in this module.
VRF names must be shorter than 32 characters and not case sensitive. 
## Examples

```yaml
---

- name: Example of how to add a vrf
  hosts: switches
  vars:
    vrfs:
      - name: management
        description: used for oob
        state: present
        admin_state: up
  roles:
    - Ansible-network_vrf

- name: Example of how to remove a vrf
  hosts: switches
  vars:
    vrfs:
      - name: management
        description: used for oob
        state: absent
  roles:
    - Ansible-network_vrf
```

## Role variables

```yaml
# Define the vrfs to be configured (see README for examples)
vrfs: { }
```


## License

Apache


## Author

Dan Murarasu
