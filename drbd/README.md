### drbd
An Ansible role to setup DRBD cluster. See https://www.linbit.com/drbd-user-guide/drbd-guide-9_0-en/ for more information. The setup process assumes that the disk
to be used by drbd is already partitioned. The install process does not handle
the partitioning.

### Requirements:
* Ansible needs to be installed on the host running this playbook. Tested on version 2.9.11.

### Platform:
* Tested on Centos 8 only

### Author:
Angelo San Ramon
