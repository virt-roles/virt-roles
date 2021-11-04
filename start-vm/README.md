# start-vm

Launch a libvirt domain and wait for SSH.

## Role Variables
|Name|Description|Type|Required|Default|
|----|-----------|----|--------|-------|
|`xml`|the libvirt domain XML (e.g. lookup('file', 'files/mydomain.xml'))|str|yes|-|
|`host`|the hostname or IP address of the domain (use static IPs or predictable DHCP)|str|yes|-|

## Example:
```yaml
- name: start VM
  include_role: start-vm
  vars:
   - domain: vm01
   - xml: "{{ lookup('file', 'files/vm01.xml') }}"
   - host: 192.168.122.192
```
