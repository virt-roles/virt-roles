# build-qemu

Build QEMU from git sources. The binaries are not installed.

# Role Variables
|Name|Description|Type|Required|Default|
|----|-----------|----|--------|-------|
|`path`|directory where the git repo is cloned|str|no|qemu|
|`repo`|git repository URL|str|no|https://gitlab.com/qemu-project/qemu.git|
|`version`|which ref to fetch from the git repository|str|no|master|
|`configure_env_vars`|environment variables for ./configure|str|no|-|
|`configure_args`|./configure command-line options|str|no|--target-list=x86_64-softmmu|

## Example
```yaml
- include_role: build-qemu
  vars:
    - repo: https://gitlab.com/qemu-project/qemu.git
    - version: master
    - configure_env_vars: AR=/path/to/ar
    - configure_args: --target-list=x86_64-softmmu
```
