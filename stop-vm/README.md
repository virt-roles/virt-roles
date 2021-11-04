# stop-vm

Stop a libvirt domain.

## Role Variables
|Name|Description|Type|Required|Default|
|----|-----------|----|--------|-------|
|`domain`|the name of the libvirt domain|str|yes|-|

## Example:
```yaml
- include_role: stop-vm
  vars:
   - domain: vm01
```
