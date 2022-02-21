snmp
====

This ansible role is to enable snmp on linux systems.
Please adjust location, contact, community and snmp v3 user/passes as needed.
In default configuration the snmpd configuration will be modified, not replaced. SNMP requests are possible from any source with snmp v2c and v3; please use a firewall to limit the accesses. 


Requirements
------------

This role has no special requirements.


Role Variables
--------------

Here is a list of variables defined in **defaults/main.yml**: 

```
# reset snmpd.conf to defaults
snmpd_config_defaults: 'no'

# device location and contact
snmp_location: 'FRA1, Interxion, Frankfurt am Main, Germany [50.11970, 8.73600]'
snmp_contact: 'Data Center <datacenter@example.com>'

# snmp agent listen address - IPv4 and IPv6 UDP
snmp_agentaddress: 'udp:161,udp6:[::1]:161'

# snmp source - accept requests from globally (default) or from network (e.g. 10.0.0.0/8)
snmp_source: 'default'

# snmp v2c community
snmp_rocommunity: 'mYsEcrEtComMuniTy01'

# snmp v3 user and passwords
snmp_v3user: 'snmpv3user'
snmp_v3authpass: 'SeCrEtAuThPaSs'
snmp_v3privpass: 'SeCrEtPrIvPaSs'

# check if snmp v2c is working on remote host
snmpd_check_v2c: 'yes'

# check if snmp v3 is working on remote host
snmpd_check_v3: 'no'
```


Dependencies
------------

This role has no dependencies.


Example Playbook
----------------

This role can be used e.g. with the following playbook:
```
---
- name: enable snmp
  hosts: linux_server
  remote_user: root
  roles:
    - christian_becker.snmp
```


License
-------

MIT


Author Information
------------------

* **Christian Becker** - [christian-becker](https://github.com/christian-becker)  

