### Vault
Ansible role to setup a Vault cluster.  

If the `vault_auto_unseal` variable is set to true, Vault will be automatically initialized and unseal. The unseal keys will be saved to a file in {{ vault_config_path }}/.vault_unseal_keys. The root token will is not saved. If the root token is needed, it can be generated using the unseal keys. See https://learn.hashicorp.com/tutorials/vault/generate-root for instructions.  

To create an initial admin account for loging in to UI, set the following variables below as an example:

```
vault_policies:
  - name: vault_admin
    policy: |-
      path "sys/health"
      {
        capabilities = ["read", "sudo"]
      }

      path "sys/policies/acl"
      {
        capabilities = ["list"]
      }

      path "sys/policies/acl/*"
      {
        capabilities = ["create", "read", "update", "delete", "list", "sudo"]
      }

      path "auth/*"
      {
        capabilities = ["create", "read", "update", "delete", "list", "sudo"]
      }

      path "sys/auth/*"
      {
        capabilities = ["create", "update", "delete", "sudo"]
      }

      path "sys/auth"
      {
        capabilities = ["read"]
      }

      path "secret/*"
      {
        capabilities = ["create", "read", "update", "delete", "list", "sudo"]
      }

      path "sys/mounts/*"
      {
        capabilities = ["create", "read", "update", "delete", "list", "sudo"]
      }

      path "sys/mounts"
      {
        capabilities = ["read"]
      }

vault_tokens:
  - id: 3b9b0360-f21e-4236-b151-baef0e6c99dd
    display_name: vault_admin
    no_default_policy: true
    no_parent: true
    policies:
      - vault_admin
```

### Requirements:
* Ansible needs to be installed on the host running this playbook. Tested on version 2.9.11.

### Platform:
* Tested on Centos 8 only

### Usage:
1. Create an inventory file for your deployment. See the [test inventory](../tests/vault/inventory) for example.
2. Create your main playbook. See the [test playbook](../tests/vault/test.yml) for example.
3. Run Ansible your playbook. Example: `ansible-playbook --ssh-extra-args="-o ConnectTimeout=10 -o ConnectionAttempts=60 -o StrictHostKeyChecking=no" -i your_inventory_file your_playbook.yml`

## Test-Kitchen Environment
### Requirements for local test-kitchen environment:
- Vagrant
- Virtualbox

### Build cluster in local test-kitchen environment:
- Install required gems: `gem install bundler && bundle install`
- Deploy: `kitchen converge`

### Author:
Angelo San Ramon