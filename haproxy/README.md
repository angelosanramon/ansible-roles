### Haproxy
Ansible role to setup HAProxy server.  
 
### Requirements:
* Ansible needs to be installed on the host running this playbook.

### Platform:
* Centos 8
* ClearLinux

## Test-Kitchen Environment
### Requirements for local test-kitchen environment:
- Vagrant
- Virtualbox

### Build cluster in local test-kitchen environment:
- Install required gems: `gem install bundler && bundle install`
- Deploy: `kitchen converge`

### Author:
Angelo San Ramon