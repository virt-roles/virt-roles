# virt-builder-create-image

Create a disk image file using virt-builder.

The disk image will have /root/.ssh/authorized_keys populated from the host so
it is possible to ssh in using the same root ssh keys as on the host.

## Role Variables
|Name|Description|Type|Required|Default|
|----|-----------|----|--------|-------|
|`os_version`|the virt-builder template to install (see virt-builder --list)|str|yes|-|
|`size`|the size of the disk (e.g. "32G")|str|yes|-|
|`output`|the path where the disk image file will be written|str|yes|-|
|`format`|the disk image file format (raw, qcow2, etc)|str|no|raw|
|`raw_opts`|additional virt-builder(1) options|str|no|-|

## Example
```yaml
- name: install Fedora 33 disk image
  include_role: virt-builder-create-image
  vars:
   - os_version: fedora-33
   - size: 32G
   - output: /var/lib/libvirt/images/fedora-33.img
   - format: raw
```
