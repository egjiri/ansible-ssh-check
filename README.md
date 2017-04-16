# Ansible Role: `egjiri.ssh-check`

A common problem is launching new VM instances and trying to provision them through Ansible before ssh connection is available. This role allows you to wait for ssh connectivity to become available before proceeding with the rest of your tasks

## Instructions

### Installation
```
ansible-galaxy install egjiri.ssh-check
```

### Usage

Set the hosts that you want to wait for ssh connectivity as part of the `ssh_check` inventor group and set the `ssh_check_active` variable to `true`. This will make the specified hosts to retry the ssh connectivity and will skip all other hosts.
A desired setup might be to leave the `ssh_check_active` as the default `false` when running the playbooks after the hosts have been up for awhile and only set it to `true` on initial provisioning when it's uncertain whether the instance is up or still booting.

## Example
```
# Make sure that your hosts have been set as part of the `ssh_check` group before this point.
# The following snippet is how you would then use the role in your Playbook

- hosts: localhost
  gather_facts: False
  vars:
    ssh_check_active: True
  roles:
  - egjiri.ssh-check
```
