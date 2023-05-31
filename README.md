# dandyrow.linux Ansible collection

[![Test Collection](https://github.com/dandyrow/dandyrow.linux/actions/workflows/test.yml/badge.svg)](https://github.com/dandyrow/dandyrow.linux/actions/workflows/test.yml)

This collection contains modules and roles to install, configure and interact with linux software.

A key module contained within this collection is the stow module. This allows Ansible to interact with the GNU stow utility. This is useful for installing dotfiles which have been organised into packages which can be expanded with said utility.

https://github.com/dandyrow/dandyrow.linux

## Contributing to this collection

The content of this collection is made by people like you, a community of individuals collaborating on making the world better through developing automation software.

We are actively accepting new contributors.

Any kind of contribution is very welcome.

If you would like to contribute please read the information in the [CONTRIBUTING](https://github.com/dandyrow/dandyrow.linux/blob/main/CONTRIBUTING.md) file.

## Governance

The final say regarding the direction of this collection remains with me, the owner of the repository, dandyrow. That being said I am open to discussions regarding new features of the collection.

## Tested with Ansible

This collection has been tested against ansible versions from 2.12.0 to 2.15.0.

## External requirements

The stow module found within this collection relies on the GNU stow utility being installed. Specifically it has been tested with version 2.3.1. This collection contains a role which will allow you to install the stow module.

## Included content

Content included within this collection can be found within the [documentation](https://dandyrow.github.io/dandyrow.linux/).

## Using this collection

### Installing the Collection from Ansible Galaxy

Before using this collection, you need to install it with the Ansible Galaxy command-line tool:
```bash
ansible-galaxy collection install dandyrow.linux
```

You can also include it in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`, using the format:
```yaml
---
collections:
  - name: dandyrow.linux
```

Note that if you install the collection from Ansible Galaxy, it will not be upgraded automatically when you upgrade the `ansible` package. To upgrade the collection to the latest available version, run the following command:
```bash
ansible-galaxy collection install dandyrow.linux --upgrade
```

You can also install a specific version of the collection, for example, if you need to downgrade when something is broken in the latest version (please report an issue in this repository). Use the following syntax to install version `2.0.0`:

```bash
ansible-galaxy collection install dandyrow.linux:==2.0.0
```

See [Ansible Using collections](https://docs.ansible.com/ansible/devel/user_guide/collections_using.html) for more details.

### Using the contents of this collection

Documentation on using the contents of this collection can be found on the collection's [docsite](https://dandyrow.github.io/dandyrow.linux/).

## Release notes

See the release notes on the [GitHub releases page](https://github.com/dandyrow/dandyrow.linux/releases).

## More information

- [dandyrow.linux Collection Documentation](https://dandyrow.github.io/dandyrow.linux)
- [Collection's Ansible Galaxy Page](https://galaxy.ansible.com/dandyrow/linux)
- [Ansible Collection overview](https://github.com/ansible-collections/overview)
- [Ansible User guide](https://docs.ansible.com/ansible/devel/user_guide/index.html)
- [Ansible Developer guide](https://docs.ansible.com/ansible/devel/dev_guide/index.html)
- [The Bullhorn (the Ansible Contributor newsletter)](https://us19.campaign-archive.com/home/?u=56d874e027110e35dea0e03c1&id=d6635f5420)
- [News for Maintainers](https://github.com/ansible-collections/news-for-maintainers)

## Licensing

GNU General Public License v3.0 or later.

See [LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.
