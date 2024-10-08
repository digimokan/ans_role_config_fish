# ans_role_config_fish

Ansible role to configure the [fish shell](https://fishshell.com/) for interactive use.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_fish.svg?label=release)](https://github.com/digimokan/ans_role_config_fish/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Configure fish colorized shell prompt.
* Add optional fish user-defined command aliases.
* NOTE: for login shell config, see [ans_role_config_shell](https://github.com/digimokan/ans_role_config_shell).

## Supported Operating Systems

* Ubuntu.
* Arch Linux.
* FreeBSD.

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_fish
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Set up fish shell for interactive use"
         ansible.builtin.include_role:
           name: ans_role_config_fish
         vars:
           user_name: "admin"
           public: true
   ```

## Role Options

Vars that must be defined when including the role in the playbook:

  * [dependencies](../defaults/main/dependencies/user.yml)

Vars with default values, which can be overridden in the playbook:

  * [overridable](../defaults/main/overridable)

Vars defined by this role, exported with `public: true`, for use in other roles:

  * [export](../defaults/main/export/commands.yml)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_fish/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

