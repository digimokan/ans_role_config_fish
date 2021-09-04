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
* [Role Dependencies](#role-dependencies)
* [Contributing](#contributing)

## Purpose

* Configure fish shell prompt, colors, and behavior.
* Optionally, set fish as user's login shell.

## Supported Operating Systems

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
           set_as_login_shell: true
   ```

## Role Options

See the role `defaults` file, for overridable vars:

  * [defaults/main.yml](../defaults/main.yml)

Define these _required_ vars for the role:

  * `user_name`: user to configure fish shell for

## Role Dependencies

* [ans_role_config_shell](https://github.com/digimokan/ans_role_config_shell)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_fish/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

