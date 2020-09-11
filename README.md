Ansible Role : Postgresqlprivs
=========

Set PostgreSQL Privileges 

Requirements
------------
No special requirements; note that this role requires root access, so either run it in a playbook with a global become: yes, or invoke the role in your playbook like:

```
- hosts: database
  roles:
    - role: notpixxl.postgresqlprivs
      become: yes
```

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

None.

Example Playbook
----------------
```
- hosts: database
  become: yes
  vars_files:
    - vars/main.yml
  roles:
    - geerlingguy.postgresql
```
Inside ```vars/main.yml```:
```
postgresql_privs
  - name: example_role
    db: example_db
    privs: SELECT,INSERT
    type: table
    objs: example_table1,example_table2
   

```
License
-------

BSD

Author Information
------------------

christophepiv@gmail.com / https://pixxlisation.tech.blog
