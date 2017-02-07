# Ansible Role: `egjiri.ssh-check`

A common problem is launching new VM instances and trying to provision them through Ansible before ssh connection is available. This role allows you to wait for ssh connectivity to become available before proceeding with the rest of your tasks

## Instructions

### Installation
```
ansible-galaxy install egjiri.ssh-check
```

### Usage

Set the hosts that you want to wait for ssh connectivity as part of the `ssh_check` inventor group. This role will skip all other hosts.

## Example
```
# Make sure that your hosts have been set as part of the `ssh_check` group before this point.
# The following snippet is how you would then use the role in your Playbook

- hosts: localhost
  gather_facts: False
  roles:
  - egjiri.ssh-check
```
