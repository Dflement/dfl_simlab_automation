# Passbolt Deployment Playbook

This Ansible playbook is designed to deploy Passbolt, an open-source password manager, on designated servers. It consists of two plays targeting different groups of hosts.

## Requirements

- Ansible installed on the control node.
- Access to target hosts via SSH with appropriate privileges.
- Docker installed on the target host(s).

## Playbook Structure

### Play 1: Initialise

- **Hosts**: All hosts
- **Become**: true
- **Roles**:
  - initialise

This play initializes the system configurations required for Passbolt deployment. It might include tasks like updating the system, setting up users, etc.

### Play 2: Passbolt Deployment

- **Hosts**: passbolt_server
- **Become**: true
- **Roles**:
  - docker_install
  - passbolt_prep
  - passbolt_start
 
- Be sure to check all the variables, and change them if needed depeding on your network/user

This play is responsible for deploying Passbolt on the designated Passbolt server. It installs Docker, prepares the system for Passbolt installation, and starts the Passbolt service.

## Usage

1. Ensure that Ansible is installed on the control node and SSH access is configured to target hosts.
2. Update the inventory file (`hosts`) with appropriate host groups and hostnames/IPs.
3. Customize any variables required by the roles in the `roles/initialise/vars/main.yml`, `roles/docker_install/vars/main.yml`, `roles/passbolt_prep/vars/main.yml` files.
4. Run the playbook using the following command:

   ```bash
   ansible-playbook install_passbook.yaml
