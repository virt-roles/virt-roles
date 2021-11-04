# virt-roles - Ansible roles for Linux KVM development

Virtualization engineers often need to create specific environments for
development and testing. Setting up software stacks including the host kernel,
QEMU, libvirt, guest operating system, and guest applications can be tedious
and time-consuming.

virt-roles is a collection of reusable Ansible roles for common operations.
Each role takes input variables that control its behavior. For example, the
following playbook creates a Fedora disk image:

```yaml
- remote_user: root
  hosts: kvm_hosts
  tasks:
    - name: install Fedora 33 disk image
      include_role: virt-builder-create-image
      vars:
        - os_version: fedora-33
        - size: 32G
        - output: /var/lib/libvirt/images/fedora.img
        - format: raw
```

## Status

I am gradually adding and extending roles as I need them in my day-to-day work.
At the moment only a limited set of roles are available.

Roles may be removed, renamed, or changed in incompatible ways, but a releases
will be published so your existing playbooks will not break.

## Contributing

Issues - Please create a GitLab Issue.
Code - Please raise a GitLab Merge Request.

## License

Licensed under the GNU General Public License 3.0 or any later version.

For questions, please email Stefan Hajnoczi \<stefanha@redhat.com\>.
