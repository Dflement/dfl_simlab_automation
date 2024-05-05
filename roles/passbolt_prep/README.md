# Passbolt Setup Role

This Ansible role sets up Passbolt, an open-source password manager, by downloading the necessary Docker Compose configuration file and generating a customized version from a template.

## Requirements

This role requires Ansible to be installed on the control node. The target host should have Docker installed and Docker Compose should be available.

## Role Variables

Before running the playbook, make sure to adjust the following variables according to your environment:

- `username`: The username under which Passbolt will be installed. This should be a valid username on the target system.

- `protocol`: The protocol used for accessing Passbolt. Typically, this is either "http" or "https".

- `ip_address`: The IP address or hostname of the server where Passbolt will be hosted.

- `port`: The port on which Passbolt will be accessible.

- `http_ports`: List of ports to be exposed by the Passbolt container. Adjust this if you need to expose additional ports.

- `docker_compose_template`: Path to the Docker Compose template file. This file will be used to generate the final Docker Compose configuration for Passbolt.

## Note

Ensure that Docker and Docker Compose are properly configured on the target system before running this role.


