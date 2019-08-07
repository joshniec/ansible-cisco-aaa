Cisco AAA
=========

This role provides a way to setup basic AAA authentication using tacacs only. Currently supported devices are NXOS, ASA and IOS(-XE). IOS-XR is not supported at this time

Requirements
------------

Ansible version 2.5 or greater

Role Variables
--------------

This role requires that the following variables be set for the host that runs this role:

```yaml
management_config:
  interface:          required
  vrf:                optional

aaa_config:
  tac_server:         required
  tac_key:            required
  tac_server_group:   required
```

Dependencies
------------

No role dependencies

Example Playbook
----------------

```yaml
- hosts: cisco_switches
  roles:
      - role: cisco_aaa
        management_config:
          - { interface: Mgmt0, vrf: Mgmt-vrf }
        aaa_config:
          - { tac_server: 1.1.1.1, tac_key: secure_key, tac_server_group: my_tac_group }
```

License
-------

MIT
