### Consul
Ansible role to setup a Consul cluster. This playbook automatically generates TLS certificates for server-to-server communication using consul tls command.

### Requirements:
* Ansible needs to be installed on the host running this playbook.

### Platform:
* Centos 8
* ClearLinux

## Test-Kitchen Environment
### Requirements for local test-kitchen environment:
- Vagrant with plugins: vagrant-guests-clearlinux
- Virtualbox

### Author:
Angelo San Ramon