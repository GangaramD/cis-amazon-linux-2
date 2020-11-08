# AmazonLinux-2-CIS - v1.0.0 - Latest

## Amazon Linux 2 - CIS Benchmark Hardening Script

This Ansible script is under development and is considered a work in progress.

This Ansible script can be used to harden a Amazon Linux 2 machine to be CIS compliant to meet level 1 or level 2 requirements.

This role will make significant changes to systems and could break the running operations of machines. Considering using this script on a test machine before using the script against other production level systems for remediation. Use this script at your own risk and no warranty is attached for the usage of this script as dictated by the license.

## System Requirements
```
Ansible 2.7+
Amazon Linux 2
```
Amazon Linux 2 and SE Linux
----------------
By default SElinux is disabled via grub in amazon linux.

The tasks in Section 1.6 of this role will enable SELinux. Alternatively, it can be manually enabled by following these steps:

edit ```/boot/grub/menu.lst```
Modifiy ```selinux=0  to  selinux=1```
```vi /etc/selinux/config```

update the SELINUX to `enforcing` save and Quit!!

Also install the following package to allow the ansible SElinux module to function on the host.
```yum install libselinux-python```

A reboot will be neccessary for the changes to take effect.


## Role
```
role: CIS_awslinux2_Benchmark
```
## Role/Playbook Tags
```
tags: 
level1
level2
always
prelim_tasks
post_tasks
```
## Section Vars
```
section1
section2
section3
section4
section5
section6
```
## Vars
```
Refer to defaults/main.yml for other vars
```
## Sample Playbook.ymls
```
Refer to CIS_awslinux2_Benchmark_(level1, level1_and_level2, or level2).ymls for sample playbook.ymls. Change the role to match role folder name.
```

## Running the playbook

```
ansible-playbook -i inventory CIS_awslinux2_Benchmark/CIS_awslinux2_Benchmark-L1-L2.yml -vv
## License
This Source Code Form is subject to the terms of the Mozilla Public
License, v. 2.0. If a copy of the MPL was not distributed with this
file, You can obtain one at https://mozilla.org/MPL/2.0/.
