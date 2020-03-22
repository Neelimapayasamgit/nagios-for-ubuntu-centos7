Role Name
=========

This role helps to install nagios on ubuntu and centos 7 servers 

Requirements
------------


Dependencies
------------

inventory:
---------

sample:
cat inventory
172.31.95.184
localhost


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

---
- hosts: all
  become: yes
  roles:
    - nagios-for-ubuntu-centos7
    
Execution:
----------

ansible-playbook -i inventory role_nagios.yml
    
sample output
-------

devops@ip-172-31-81-12:~$ ansible-playbook -i inventory role_nagios.yml

PLAY [all] **********************************************************************************************************************************************************************************

TASK [Gathering Facts] **********************************************************************************************************************************************************************
[DEPRECATION WARNING]: Distribution Ubuntu 18.04 on host localhost should use /usr/bin/python3, but is using /usr/bin/python for backward compatibility with prior Ansible releases. A
future Ansible release will default to using the discovered platform python for this host. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more
 information. This feature will be removed in version 2.12. Deprecation warnings can be disabled by setting deprecation_warnings=False in ansible.cfg.
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Include OS-specific variables.] ***************************************************************************************************************************
ok: [172.31.95.184]
ok: [localhost]

TASK [nagios-for-ubuntu-centos7 : Include main nagios variables.] ***************************************************************************************************************************
ok: [172.31.95.184]
ok: [localhost]

TASK [nagios-for-ubuntu-centos7 : update cache for ubuntu] **********************************************************************************************************************************
skipping: [172.31.95.184]
changed: [localhost]

TASK [nagios-for-ubuntu-centos7 : install packages of os specific] **************************************************************************************************************************
ok: [localhost] => (item=autoconf)
ok: [localhost] => (item=gcc)
ok: [localhost] => (item=libc6)
ok: [localhost] => (item=make)
ok: [localhost] => (item=wget)
ok: [localhost] => (item=unzip)
ok: [172.31.95.184] => (item=gcc)
ok: [localhost] => (item=apache2)
ok: [localhost] => (item=php)
ok: [localhost] => (item=libapache2-mod-php7.2)
ok: [localhost] => (item=libgd-dev)
ok: [localhost] => (item=libmcrypt-dev)
ok: [localhost] => (item=libssl-dev)
ok: [172.31.95.184] => (item=glibc)
ok: [localhost] => (item=bc)
ok: [localhost] => (item=gawk)
ok: [localhost] => (item=dc)
ok: [localhost] => (item=build-essential)
ok: [localhost] => (item=snmp)
ok: [172.31.95.184] => (item=glibc-common)
ok: [localhost] => (item=libnet-snmp-perl)
ok: [localhost] => (item=gettext)
ok: [172.31.95.184] => (item=wget)
ok: [172.31.95.184] => (item=unzip)
ok: [172.31.95.184] => (item=httpd)
ok: [172.31.95.184] => (item=gd)
ok: [172.31.95.184] => (item=gd-devel)
ok: [172.31.95.184] => (item=perl)
ok: [172.31.95.184] => (item=postfix)
ok: [172.31.95.184] => (item=make)
ok: [172.31.95.184] => (item=automake)
ok: [172.31.95.184] => (item=gettext)
ok: [172.31.95.184] => (item=autoconf)
ok: [172.31.95.184] => (item=openssl-devel)
ok: [172.31.95.184] => (item=net-snmp)
ok: [172.31.95.184] => (item=net-snmp-utils)
ok: [172.31.95.184] => (item=perl-Net-SNMP)

TASK [nagios-for-ubuntu-centos7 : Download the source to temp folder] ***********************************************************************************************************************
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : untar the code] *******************************************************************************************************************************************
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Download the plugin to temp folder] ***********************************************************************************************************************
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : untar the plugin code] ************************************************************************************************************************************
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Compile Code] *********************************************************************************************************************************************
[WARNING]: Consider using 'become', 'become_method', and 'become_user' rather than running sudo
changed: [localhost]
changed: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Create User and Group] ************************************************************************************************************************************
changed: [localhost]
changed: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Install nagios specific binaries] *************************************************************************************************************************
changed: [localhost] => (item=install)
changed: [localhost] => (item=install-daemoninit)
changed: [localhost] => (item=install-commandmode)
changed: [localhost] => (item=install-config)
changed: [localhost] => (item=install-webconf)
changed: [172.31.95.184] => (item=install)
changed: [172.31.95.184] => (item=install-daemoninit)
changed: [172.31.95.184] => (item=install-commandmode)
changed: [172.31.95.184] => (item=install-config)
changed: [172.31.95.184] => (item=install-webconf)

TASK [nagios-for-ubuntu-centos7 : Install Apache Config Files] ******************************************************************************************************************************
skipping: [172.31.95.184]
changed: [localhost]

TASK [nagios-for-ubuntu-centos7 : Install latest passlib with pip] **************************************************************************************************************************
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Create nagiosadmin user account] **************************************************************************************************************************
ok: [localhost]
ok: [172.31.95.184]

TASK [nagios-for-ubuntu-centos7 : Compile + Install] ****************************************************************************************************************************************
changed: [localhost]


changed: [172.31.95.184]

RUNNING HANDLER [nagios-for-ubuntu-centos7 : restart services] ******************************************************************************************************************************
changed: [localhost] => (item=apache2)
changed: [localhost] => (item=nagios)
changed: [172.31.95.184] => (item=httpd)
changed: [172.31.95.184] => (item=nagios)

PLAY RECAP **********************************************************************************************************************************************************************************
172.31.95.184              : ok=15   changed=5    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0
localhost                  : ok=17   changed=7    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0



Author Information
------------------
Neelima Payasam.
