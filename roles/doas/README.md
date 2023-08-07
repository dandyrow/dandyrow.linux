Ansible Role - Doas
=========

Ansible role to replace sudo with doas from OpenBSD.

Install from Ansible Galaxy using this command: `ansible-galaxy install dandyrow.doas`

View Ansible Galaxy page [here](https://galaxy.ansible.com/dandyrow/doas).

This role uninstalls sudo after it checks to make sure the syntax of doas.conf is correct. I am not responsible if you get locked out of root privileges due to a mistake you made in the contents of the doas conf file. Sudo will not be uninstalled if the syntax is incorrect in doas.conf.

Dependencies
------------

This role depends on the community.general collection to work. This is usually installed alongside Ansible on a system.

Role Variables
--------------

See [dandyrow.linux collection documentation](https://dandyrow.github.io/dandyrow.linux/doas_role.html) for role variables.

Supported Platforms
-------------------

* Arch Linux
* Debian 11 Bullseye
* Ubuntu 22.04 Jammy Jellyfish (might work with 22.10 but not tested)

Example Playbook
----------------

The following example shows how to run the role:

```yaml
    - name: Replace sudo with doas keeping sudoers file
      hosts: all
      roles:
        - role: doas
          vars:
            doas_conf_lines:
              - permit arthur
              - permit persist :wheel
```

Each item in the array doas_conf will be added as a line in the doas config file on the target host. See the [doas.conf(5)](https://man.archlinux.org/man/doas.conf.5.en) for information on how to configure doas.

License
-------

GPL-3.0-only

Author Information
------------------

Created by Daniel Lowry (dandyrow). 

Email: [development@daniellowry.co.uk](mailto:development@daniellowry.co.uk)
