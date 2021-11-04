# build-kernel

Build a kernel from git sources with a given .config file. The `make
olddefconfig all` make command is invoked. The kernel is not installed.

## Role Variables
|Name|Description|Type|Required|Default|
|----|-----------|----|--------|-------|
|`repo`|git repository URL|str|no|https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git|
|`version`|which ref to fetch from the git repository|str|no|master|
|`config_src_path`|the local .config file path|str|no|files/.config|

## Example
```yaml
- name: build kernel
  include_role: build-kernel
  vars:
    - repo: https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
    - version: master
    - config_src_path: files/.config
```
