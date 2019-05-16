# ansible-ubuntu-ntp

[Ansible](https://www.ansible.com/) Roles I use to provision Network Time Protocol (NTP) on a fresh Ubuntu server.

Personal use but maybe worthwhile for you as well.

Checkout my `https://github.com/justb4/ansible-ubuntu-base` Role as well, for installing
and securing basic stuff on a fresh Ubuntu server.
 
For more advanced stuff like adding Users, Postfix Docker I use great Roles from Ansible Galaxy:

* Users, Groups, Sudoers: https://galaxy.ansible.com/sansible/users_and_groups 
* Docker and -Compose: https://galaxy.ansible.com/geerlingguy/docker
* Postfix: https://galaxy.ansible.com/oefenweb/postfix
* Python Pip: https://galaxy.ansible.com/geerlingguy/pip (Again that Geerling Guy, he's amazing!) 

## Install

```bash

 ansible-galaxy install https://github.com/justb4/ansible-ubuntu-ntp
 
 # or locally in specific dir
 
 ansible-galaxy install --roles-path ./roles https://github.com/justb4/ansible-ubuntu-ntp


```

## Example Playbook

This sketches how I use this with the `ubuntu-base-role`.

```yaml

- name: "Standard Ubuntu Server Setup"
  hosts: all
  become: true
  gather_facts: yes

  roles:

    - name: ansible-ubuntu-base
      tags: ubuntu-base

    - name: ansible-ubuntu-ntp
      tags: ubuntu-ntp

```

## Links

* https://www.tutorialspoint.com/ansible

## Credits

* Initial Inspiration: https://github.com/5car1z/ansible-debian-provisioning
* [Jeff Geerling, geerlingguy](https://galaxy.ansible.com/geerlingguy) buy his book [Ansible for Devops](https://leanpub.com/ansible-for-devops) on LeanPub to support him!

