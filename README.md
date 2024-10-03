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

Install and name it `justb4.ubuntu-ntp`.

```bash

 ansible-galaxy install https://github.com/justb4/ansible-ubuntu-nt,,justb4.ubuntu-ntp,,justb4.ubuntu-ntp
 
 # or locally in specific dir
 
 ansible-galaxy install --roles-path ./roles https://github.com/justb4/ansible-ubuntu-ntp,,justb4.ubuntu-ntp


```

Or with a typical `requirements.yml` file:

```
# Installs from Ansible galaxy
- src: sansible.users_and_groups
  version: v2.0.5

- src: geerlingguy.pip
  version: 3.0.3

- src: geerlingguy.docker
  version: 7.4.1

# from GitHub
- src: https://github.com/justb4/ansible-ubuntu-base
  name: justb4.ubuntu-base
  version: v1.5

- src: https://github.com/justb4/ansible-ubuntu-ntp
  name: justb4.ubuntu-ntp
  version: v1.0

```

## Example Playbook

This sketches how I use this with the `ubuntu-base-role`.

```yaml

- name: "Standard Ubuntu Server Setup"
  hosts: all
  become: true
  gather_facts: yes

  roles:

    - name: justb4.ubuntu-ntp
      tags: ubuntu-ntp

```

## Links

* https://www.tutorialspoint.com/ansible

## Credits

* Initial Inspiration: https://github.com/5car1z/ansible-debian-provisioning
* [Jeff Geerling, geerlingguy](https://galaxy.ansible.com/geerlingguy) buy his book [Ansible for Devops](https://leanpub.com/ansible-for-devops) on LeanPub to support him!

