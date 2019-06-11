Ansible Role: Wildfly
=====================

This role install Wildfly (default: latest) on Centos7.

Access from:
- http://ip:8080       
- http://ip:9990       
- https://ip:9990:8443 

Credentials:
- User: admin
- Pass: password

Versions: https://wildfly.org/downloads/
- 16.0.0
- 15.0.1
- 15.0.0
- ...
  
Requirements
------------

This Ansible playbook is meant to be run on a FRESH never used server, virtual machine or container.

Role Variables
--------------

**defaults/main.yml:***
```
wildfly_packages:
  - java-1.8.0-openjdk-devel
  - unzip
  - python2-pip

wildfly_wildfly_version: '16.0.0'
wildfly_wildfly_install: '/opt/wildfly'
```

Role Templates
==============

```
wildfly_service.j2
```

Dependencies
------------

None.

Example Playbook
----------------

**Example with prompt:**
```
- hosts: "{{ vm }}"
  gather_facts: True

  vars_prompt:
    - name: "vm"
      prompt: "VM"
      private: no

  roles:
    - { role: squintans.wildfly }
```

Playbook Call
=============
```
ansible-playbook -i inventory.yml play.yml
```

License
-------

BSD

Author Information
------------------
This role was created in 2019 by Serafín Quintáns - [@squintans](http://www.linkedin.com/in/serafin-quintans/)

