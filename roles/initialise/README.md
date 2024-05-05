# System Update and Configuration Role

This Ansible role updates the server packages, installs Neovim, Chrony, and configures the timezone.

## Requirements

This role requires Ansible to be installed on the control node.

## Role Variables

The following variables can be defined in your playbook or inventory file:

- `timezone`: Specifies the desired timezone. Default is `"UTC"`.

## Handlers

This role includes the following handlers:

- `Restart Chrony service`: Restarts the Chrony service after changing the timezone.

## Dependencies

This role depends on the `community.general.timezone` Ansible collection to configure the timezone.

