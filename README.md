# Ansible Playbook: Add Volume to Volume Group

## Overview
This Ansible playbook is used to manage volumes and volume groups in IBM FlashSystem. It:
1. Authenticates to the IBM FlashSystem.
2. Retrieves a list of all volumes and host mappings.
3. Identifies volumes that are not part of any volume group.
4. Creates necessary volume groups.
5. Adds volumes to their corresponding volume groups.

## Prerequisites
- Ansible 2.9 or higher
- IBM FlashSystem collection for Ansible (`ibm.storage_virtualize`)
- Vault file (`vault.yml`) with the following variables:
  - `vault_username`
  - `vault_password`

## Variables
- `clustername`: Name of the IBM FlashSystem cluster.
- `domain`: Domain of the IBM FlashSystem.
- `vault_username`: Username for authentication (stored in `vault.yml`).
- `vault_password`: Password for authentication (stored in `vault.yml`).

## Usage
1. Ensure you have the necessary prerequisites.
2. Update the `vault.yml` file with your credentials.
3. Run the playbook:
   ```bash
   ansible-playbook playbook.yml
