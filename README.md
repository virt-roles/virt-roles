# virt-tasks - Ansible tasks for Linux KVM development

Virtualization engineers often need to create specific environments for
development and testing. Setting up specific software stacks including the host
kernel, QEMU, libvirt, guest operating system, and guest applications can be
tedious and time-consuming.

virt-tasks is a collection of reusable Ansible tasks for common operations. Each
task is documented and takes input `vars` that control its behavior. For
example, the following playbook uses virt-tasks to create a Fedora 33 disk
image:

```yaml
- remote_user: root
  hosts: kvm_hosts
  tasks:
    - name: install Fedora 33 disk image
      include_tasks: virt-tasks/tasks/virt-builder-create-image.yml
      vars:
        - os_version: fedora-33
        - size: 32G
        - output: /var/lib/libvirt/images/fedora-33.img
        - format: raw
```

To see the available tasks, look in the `tasks/` directory. Each task includes
documentation at the top of the file.

## Status

I am gradually adding reusable tasks as I need them in my day-to-day work. At
the moment virt-tasks only offers a limited set of tasks.

Tasks may be removed, renamed, or changed in incompatible ways, but a
virt-tasks release will be published so your existing playbooks will not break.

## Contributing

Issues - Please create a GitLab Issue.
Code - Please raise a GitLab Merge Request.

## License

virt-tasks is licensed under the GNU General Public License 3.0 or any later
version.

For questions about virt-tasks, please email Stefan Hajnoczi \<stefanha@redhat.com\>.
