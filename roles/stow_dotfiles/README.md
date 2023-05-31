Ansible Role - stow_dotfiles
=========

Ansible role to install a set of dotfiles from a Git repo using the stow command. The dotfiles repo should be layed out into folders to allow GNU stow to place them in the correct locations. For an example of this please see my [personal dotfiles repo](https://github.com/dandyrow/dotfiles).

Requirements
------------

Requires the git and stow packages but these will be installed by the role if not already installed on the target host.

Role Variables
--------------

The default values of each variable are shown after the colon.

The following variables are declared in defaults/main.yml:

`dotfiles_remote_repo: ''` - URL of dotfiles repo to install dotfiles from. Set to my dotfiles repo by default.

`dotfiles_local_repo: ~/.dotfiles` - Local path where dotfiles repo will be cloned to. Defaults to .dotfiles folder within the home directory of the user ansible is executing as.

`dotfiles_pull_single_branch: true` - Whether to pull all branches from the dotfiles repo. Use the next variable to set which branch to pull if this is set to true.

`dotfiles_repo_branch: master` - Which branch to pull from. Useful when used in conjunction with the previous variable to set which branch to pull.

`dotfiles_target_path: ~/` - Target location to install dotfiles to. This will usually be the target user's home folder. This path can be change to `/home/<username>` to allow this role to be run as other users than the installation user. Can also be changed to `/etc/<package-name>` for installing config files in system wide config directories, e.g. pacman config.

`dotfiles_to_install: []` - List of names of folders within dotfiles repo to install to the target path.

The following variable can be found in vars/main.yml:

`required_packages: [ git, stow ]` - Name of packages required to be installed on target host to use this role. Role will install these packages on the target host if they aren't already present.

Dependencies
------------

This role is part of and depends on the [dandyrow.linux collection.](https://github.com/dandyrow/dandyrow.linux)

Example Playbook
----------------

To use this role in a playbook change the `dotfiles_repo` variable to the URL of the dotfiles repo you want to install dotfiles from and set which dotfiles you want to install in the `dotfiles_to_install` list.
```yaml
    - hosts: servers
      roles:
         - role: dandyrow.dotfiles_stow
           vars:
             dotfiles_repo: https://github.com/<GitHub_username>/<repo_name>.git
             dotfiles_to_install:
              - zsh
              - git
```
License
-------

GPL-3.0-only

Author Information
------------------

This role was created in 2023 by Daniel Lowry as part of a wider personal infrastructure as code project.

Developer email: [development@daniellowry.co.uk](mailto:development@daniellowry.co.uk)
