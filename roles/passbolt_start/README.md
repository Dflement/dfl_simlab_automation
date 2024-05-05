# Passbolt Start Role

This Ansible role starts the Passbolt service after the necessary setup steps have been completed.

## Requirements

This role requires Ansible to be installed on the control node. The target host should have Docker installed and the Passbolt setup should be completed.

## Role Variables

Before running the playbook, make sure to adjust the following variables according to your environment:

- `username`: The username under which Passbolt is installed. This should be the same as the username used in the `passbolt_setup` role.

- `waiting_time`: The time (in seconds) to wait for the database to set up before registering the Passbolt user.

## Note

Ensure that Passbolt setup has been completed before running this role.

