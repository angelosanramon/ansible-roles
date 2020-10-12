### Keepalived
Ansible role to install and configure Keepalived for setting up highly-available
cluster.

### Requirements:
* Ansible needs to be installed on the host running this playbook. Tested on version 2.9.11.

### Platform:
* Tested on Centos 8 only

### Usage:
1. Create an inventory file for your deployment. See the [test inventory](../tests/haproxy-keepalived/inventory) for example.
2. Create your main playbook. See the [test playbook](../tests/haproxy-keepalived/test.yml) for example.
3. Run Ansible your playbook. Example: `ansible-playbook --ssh-extra-args="-o ConnectTimeout=10 -o ConnectionAttempts=60 -o StrictHostKeyChecking=no" -i your_inventory_file your_playbook.yml`

### Author:
Angelo San Ramon